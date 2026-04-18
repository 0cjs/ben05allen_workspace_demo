Combined Virtualenv
-------------------

The `Test` script sets up the virtualenv for each package under `packages/`
and also a top-level virtualenv that brings in all packages. (The
virtualenvs are under `.build/virtualenv/` in the top level and each
package directory.) It uses [`pactivate`] which bootstraps Pip and the
virtualenv package, creates a virtualenv in `.build/virtualenv`, and
installs everything listed in `requirements.txt` into that virtualenv.\
(Pactivate isn't anything special; it just uses the standard Python `pip`
and `virtualenv` tools.)

The "tests" run by this are merely to `pip list` each virtualenv.

You can activate any of these virtualenv in your own shell using the
standard ` source .build/virtualenv/bin/activate` incatation (or the
appropriate file for your shell).

It's unclear to cjs how the top level vitualenv is different from what
`[tool.uv.workspace]` does. It would be interesting also to see how you
would have this `Test` script use `uv` and workspaces to do this same `pip
list` for each virtualenv specified by `requirements.txt` and
`packages/*/requirements.txt`.



<!-------------------------------------------------------------------->
[`pactivate`]: https://github.com/cynic-net/pactivate
