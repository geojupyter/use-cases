# GeoJupyter Use Cases

This is a depository of GeoJupyter community use cases.

This includes existing workflows or processes that need improvement or ideas for new
workflows or processes that could enable new ways of thinking and working with
geospatial data.

Pull requests are more than welcome :D


## Contributing

### Request a use case

Please open a GitHub issue with a _very_ detailed description of your use case.
A good example of the level of detail we're looking for can be found in
[this comment by `@brookisme`](https://github.com/geojupyter/jupytergis/issues/436#issuecomment-2637601373)!


### Add your use case yourself!

#### Fork the repository

Click the fork button towards the top of the GitHub repository home page.
In your fork repository, create a new branch to contain your work.


#### Add a new use case

In your new branch on your fork:

* Add a new use case directory to the root of this repository
* Create an `index.md` file within
* Ensure your document has a descriptive and concise title (`h1` header) at the first
  line, in sentence case, e.g.:

  ```markdown
  # My use case title
  ```

* Have two `h2` sub-headers: `## Current situation` (describe the problem) and
  `## Proposed improvement` (describe a potential solution).
  The "proposed improvement" header can have multiple options as `h3` headers, e.g.
  `### Option A`, `### Option B`, etc.
* If you have any ancillary files, e.g. diagrams, screenshots, sketches, or animations,
  to go with your use case, include those in your new use case directory.


#### Validation checks

We use [`pre-commit`](https://pre-commit.com/) to run validation checks on this repository.

You can either install `pre-commit` locally (e.g. `pixi global install pre-commit` or
`uv tool install pre-commit`), or run pre-commit in your pull request with a comment
containing the text `pre-commit.ci autofix`.
The latter option won't autofix every problem; some must be fixed manually (e.g.
spelling fixes).


#### Open a pull request

Open a pull request targeting the `main` branch of this repository.
Someone will review it as soon as they can!
