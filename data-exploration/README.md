# data-exploration

## Setup

You will need a modern version of Python (tested on 3.11.3). Install the dependencies:

```bash
pip install -r requirements.txt
```

`jupyter-nbconvert` also requires Pandoc. Check if you have it installed:

```bash
pandoc --version
```

If you don't have it, [install it first](https://pandoc.org/installing.html) before converting the notebook to HTML.

## Converting to HTML

If you have GNU Make, just run:

```bash
make
```

If not,

```bash
jupyter nbconvert --to html --output index cs132_data_exploration.ipynb
```

If you're converting a notebook downloaded from Google Colab, `jupyter-nbconvert` will throw a `KeyError` regarding the notebook's metadata. You will need to remove the `widgets` key from the metadata, either through a text editor or using the `jq` command (install from [here](https://stedolan.github.io/jq/download/)):

```bash
jq -M 'del(.metadata.widgets)' cs132_data_exploration.ipynb > input.ipynb
```

Then convert to HTML:

```bash
jupyter nbconvert --to html --output index input.ipynb
```

If you have GNU Make, you can just run `make from-colab` instead of the above.
