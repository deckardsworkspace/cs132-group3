all: convert

convert: execute to-html
from-colab: execute-colab to-html

execute:
	python -m jupyter nbconvert --inplace --execute \
		--output index data_exploration.ipynb

execute-colab: fix-json
	python -m jupyter nbconvert --inplace --execute \
		--output index fixed.ipynb

to-html:
	python -m jupyter nbconvert --to html \
		--output data_exploration --HTMLExporter.theme=dark index.ipynb
	sed --in-place=.orig \
		's/<title>.*<\/title>/<title>G3 Portfolio \| Data Exploration<\/title>/g' \
		data_exploration.html

fix-json:
	jq -M 'del(.metadata.widgets)' data_exploration.ipynb \
		> fixed.ipynb

clean:
	rm -f input.ipynb index.ipynb index.html
