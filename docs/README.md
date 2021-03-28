# SmallDict Documentation

Available at:
https://smalldict.readthedocs.io/

## How to generate the Sphinx documentation for Read the Docs

1. Install dependencies
```bash
pip install smalldict[docs]
```

2. Generate rst (reStructuredText) files for API based on docstrings
```bash
cd <repository>/docs
sphinx-apidoc --module-first -o ./ ../src/smalldict -f
```

3. Split the repository top README.md into smaller markdown files

```bash
cd <repository>/docs
csplit -f 'section' -b %02d.md -n 2 ../README.md "/^## /" {*}
``` 

4. Optional: Generate HTML files to review locally before pushing to the repository

```bash
cd <repository>/docs
make html
```
