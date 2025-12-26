# Explore multiple datasets together

## Current situation

The user experience for exploring datasets currently drives many Jupyter users to open
QGIS or ArcGIS to explore their data, and they report friction switching between
applications.

Some current tools aren't quite meeting user needs, e.g.:

* `my_gdf.explore()`: Only shows one dataset at a time
* `my_dataarray.plot()`: Shows one dataset, non-interactive
* JupyterGIS: Symbology configuration is manual and low-level
* `ipyleaflet`: Low-level. Can't render Xarray DataArrays dynamically (see possible
  solution: <https://github.com/davidbrochart/xarray_leaflet>)


## Proposed improvement

Prototype: <https://github.com/geojupyter/jupyter-microgis>

Add layers to a map for exploration within a Jupyter Notebook:

```python
from ... import explore

explore(
    my_xarray_dataarray,
    {'data': my_geodataframe, 'symbology': 'choropleth'},
)
```

* Support rioxarray DataArrays
* Support geopandas GeoDataFrames
* Maybe: Support WMTS?
* Support some curated default symbology options
    * Choropleth: number of steps, classification mode, ?
    * Symbol map: shape, min/max size, ...
    * Dot density: ...
    * Cartogram: Maybe?
* Support some symbology customization
    * Each symbology option provides sensible defaults and allows for detailed
      customization if desired.
      The point isn't to help people make maps for publication, though.
      We're choosing to trade off user control so we can have a simpler API.
* Use a Jupyter Server extension to tile raster data under the covers, e.g.
  [rioxarray DataArray -> TiTiler](https://developmentseed.org/titiler/packages/xarray/)
* Send vector data to the renderer as binary (geoarrow)
* Future integration (developed as an independent component): Support a data discovery
  interface which can help the user find other data they want to integrate with their
  Notebook analysis
    * Plain language search
    * Produce Python one-liners to bring that dataset into their notebook, e.g. `geopandas.read_file(...)` and `xarray.open_mfdataset(...)`
* Display the data on slippy map widget (e.g. DeckGL)


## Questions

### Is this `leafmap`?

Is this idea basically [`leafmap`](https://leafmap.org/)?
If we add support to directly visualize xarray datasets with TiTiler in leafmap, does
that meet the goals of this use case?
