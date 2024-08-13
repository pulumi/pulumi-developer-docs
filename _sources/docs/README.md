# Pulumi developer documentation

Welcome to the Pulumi developer documentation! This site is designed to provide
complete documentation for maintainers of and contributors to Pulumi.
Documentation is built with [Sphinx](https://www.sphinx-doc.org) and authored in
Markdown as much as possible. Markdown support for Sphinx is provided by
[MyST](https://myst-parser.readthedocs.io), which provides a number of
extensions to the Markdown dialect you may be used to in order to take advantage
of various Sphinx features.

## Workflow

### Building

The `docs` directory contains a `Makefile` (<gh-file:pulumi#docs/Makefile>) for
working with the documentation. Generally you'll just want:

```sh
make -C docs watch
```

which will watch for changes and rebuild the documentation as needed, serving
the results at http://localhost:8000. If you want to build the documentation
without watching for changes, you can use the `build` target instead:

```sh
make -C docs build
```

`build` will compile documentation to a static HTML website in the `docs/_build`
directory; you can open the `README.html` file in your browser to view the built
files from there:

```sh
open docs/_build/docs/README.html
```

### Deploying

This documentation is currently built using the `build` target and then shipped
to GitHub pages under the `pulumi-developer-docs` repository. It is publicly
available at <https://pulumi-developer-docs.github.io> as a result. Changes are
built automatically as part of every pull request raised against the
`pulumi/pulumi` repository and deployed on merge. See the `ci-docs` workflow at
<gh-file:pulumi#.github/workflows/ci-docs.yml> for more information.

```{toctree}
:maxdepth: 1
:titlesonly:

/docs/writing
/docs/diagrams
```
