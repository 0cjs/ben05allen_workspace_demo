Combined Virtualenv
-------------------

The `Test` script merely sources `pactivate`, which bootstraps Pip and
the virtualenv package, creates a virtualenv in `.build/virtualenv`, and
installs everything listed in `requirements.txt` into that virtualenv.
(Normally after this the `Test` script would run some tests.)

You can also activate within your own shell using `source ./pactivate`.

It's unclear to cjs how this is different from what `[tool.uv.workspace]`
does.
