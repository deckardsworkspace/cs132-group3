# notebooks

## Setup

You will need Python version 3.11 or newer. Install the dependencies:

```bash
pip install -r requirements.txt
```

If you're running macOS, use the following command instead:

```bash
pip install -r requirements-macos.txt
```

This requirement list omits libraries not available on macOS, specifically those that require an NVIDIA GPU.

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
python -m jupyter nbconvert --to html --output index <notebook>.ipynb
```

If you're converting a notebook downloaded from Google Colab, `jupyter-nbconvert` will throw a `KeyError` regarding the notebook's metadata. You will need to remove the `widgets` key from the metadata, either through a text editor or using the `jq` command (install from [here](https://stedolan.github.io/jq/download/)):

```bash
jq -M 'del(.metadata.widgets)' <notebook>.ipynb > input.ipynb
```

Then convert to HTML:

```bash
jupyter nbconvert --to html --output index input.ipynb
```

If you have GNU Make, you can just run `make from-colab` instead of the above.
