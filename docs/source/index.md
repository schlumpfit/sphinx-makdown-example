# Setup new sphinx project with markdown support

## Project setup

Setup new python environment
```
pyenv update
pyenv install 3.10.0
pyenv local 3.10.0
```

Add poetry
```
pip3 install poetry
```

Create new poetry project
```
poetry new sphinx-doc
cd sphinx-doc
poetry add sphinx
```

Create new sphinx project
```
sphinx-quickstart docs
```

## Add markdown support

Add dependencies
```
poetry add myst-parser
```

Change configuration under `docs/source/conf.py` and add:
```
extensions = ['myst_parser']
```

If you want to use Markdown files with extensions other than .md, adjust the source_suffix variable:
```
source_suffix = {
    '.rst': 'restructuredtext',
    '.txt': 'markdown',
    '.md': 'markdown',
}
```

## Change Layout to sphinx-material

Resource: https://bashtage.github.io/sphinx-material/index.html

Install layout:
```
poetry install sphinx-material
```

Change configuration under `docs/source/conf.py`:
```
html_theme = 'sphinx_material'
```

## Build and show html

Inside `./docs` run:
```
poetry run make html
```

Display index file:
```
xdg-open docs/source/index.html
```


