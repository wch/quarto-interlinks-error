To reproduce the problem:


```bash
python -m venv venv
. venv/bin/activate
pip install quartodoc
quarto render
```

The output:

```
$ quarto render
pandoc
  to: html
  output-file: test.html
  standalone: true
  section-divs: true
  html-math-method: mathjax
  wrap: none
  default-image-extension: png

metadata
  document-css: false
  link-citations: true
  date-format: long
  lang: en
  title: Input controls

Traceback (most recent call last):
  File "/Users/winston/quarto-interlinks-error/_extensions/machow/interlinks/interlinks.py", line 212, in prepare
    interlinks = meta["interlinks"]
                 ~~~~^^^^^^^^^^^^^^
KeyError: 'interlinks'

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/Users/winston/quarto-interlinks-error/_extensions/machow/interlinks/interlinks.py", line 274, in <module>
    main()
  File "/Users/winston/quarto-interlinks-error/_extensions/machow/interlinks/interlinks.py", line 270, in main
    return pf.run_filter(visit, prepare=prepare, doc=None)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Users/winston/quarto-interlinks-error/venv/lib/python3.11/site-packages/panflute/io.py", line 227, in run_filter
    return run_filters([action], *args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Users/winston/quarto-interlinks-error/venv/lib/python3.11/site-packages/panflute/io.py", line 203, in run_filters
    prepare(doc)
  File "/Users/winston/quarto-interlinks-error/_extensions/machow/interlinks/interlinks.py", line 214, in prepare
    raise ConfigError(
ConfigError: No interlinks.sources field detected in your metadata.Please add this to your header:

interlinks:
 sources:
    - <source_name>: {url: ..., inv: ..., fallback: ... }
Error running filter /Users/winston/quarto-interlinks-error/_extensions/machow/interlinks/interlinks.py:
Filter returned error status 1
(venv)
```