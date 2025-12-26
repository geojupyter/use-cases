# Explore multiple datasets together

Prototype: <https://github.com/geojupyter/jupyter-microgis>

* Add layers to a map for exploration from a Jupyter Notebook:

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
