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
Check file:///Users/winston/nobackup/quarto-cli/src/quarto.ts
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

Error running filter /Users/winston/nobackup/quarto-cli/src/resources/filters/main.lua:
Block expected, got Attr
	while retrieving MetaValue
	while retrieving value
	while retrieving key-value pair
	while retrieving Map
	while retrieving MetaValue
	while retrieving value
	while retrieving key-value pair
	while retrieving Map
	while retrieving MetaValue
	while retrieving index 1
	while retrieving list
	while retrieving function argument values
	while retrieving arguments for function MetaList
stack traceback:
	...to-cli/src/resources/filters/./common/wrapped-filter.lua:79: in function <...to-cli/src/resources/filters/./common/wrapped-filter.lua:77>
	[C]: in ?
	[C]: in method 'walk'
	...to-cli/src/resources/filters/./common/wrapped-filter.lua:69: in function <...to-cli/src/resources/filters/./common/wrapped-filter.lua:64>
	[C]: in ?
	[C]: in method 'walk'
	...p/quarto-cli/src/resources/filters/./ast/customnodes.lua:140: in function 'run_emulated_filter'
	.../quarto-cli/src/resources/filters/./ast/runemulation.lua:11: in local 'callback'
	.../quarto-cli/src/resources/filters/./ast/runemulation.lua:16: in upvalue 'run_emulated_filter_chain'
	.../quarto-cli/src/resources/filters/./ast/runemulation.lua:57: in function <.../quarto-cli/src/resources/filters/./ast/runemulation.lua:38>
stack traceback:
	...to-cli/src/resources/filters/./common/wrapped-filter.lua:69: in function <...to-cli/src/resources/filters/./common/wrapped-filter.lua:64>
	[C]: in ?
	[C]: in method 'walk'
	...p/quarto-cli/src/resources/filters/./ast/customnodes.lua:140: in function 'run_emulated_filter'
	.../quarto-cli/src/resources/filters/./ast/runemulation.lua:11: in local 'callback'
	.../quarto-cli/src/resources/filters/./ast/runemulation.lua:16: in upvalue 'run_emulated_filter_chain'
	.../quarto-cli/src/resources/filters/./ast/runemulation.lua:57: in function <.../quarto-cli/src/resources/filters/./ast/runemulation.lua:38>
stack traceback:
	...p/quarto-cli/src/resources/filters/./ast/customnodes.lua:140: in function 'run_emulated_filter'
	.../quarto-cli/src/resources/filters/./ast/runemulation.lua:11: in local 'callback'
	.../quarto-cli/src/resources/filters/./ast/runemulation.lua:16: in upvalue 'run_emulated_filter_chain'
	.../quarto-cli/src/resources/filters/./ast/runemulation.lua:57: in function <.../quarto-cli/src/resources/filters/./ast/runemulation.lua:38>
ERROR: Error
    at renderFiles (file:///Users/winston/nobackup/quarto-cli/src/command/render/render-files.ts:538:23)
    at async renderProject (file:///Users/winston/nobackup/quarto-cli/src/command/render/project.ts:263:23)
    at async Command.fn (file:///Users/winston/nobackup/quarto-cli/src/command/render/cmd.ts:211:26)
    at async Command.execute (file:///Users/winston/nobackup/quarto-cli/src/vendor/deno.land/x/cliffy@v0.25.4/command/command.ts:1790:7)
    at async quarto (file:///Users/winston/nobackup/quarto-cli/src/quarto.ts:122:3)
    at async file:///Users/winston/nobackup/quarto-cli/src/quarto.ts:154:5
```