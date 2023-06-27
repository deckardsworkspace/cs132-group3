all: convert

convert: execute to-html
from-colab: execute-colab to-html

execute:
	python -m jupyter nbconvert --inplace --execute \
		--output index results.ipynb

execute-colab: fix-json
	python -m jupyter nbconvert --inplace --execute \
		--output index fixed.ipynb

to-html:
	python -m jupyter nbconvert --to html \
		--output index --HTMLExporter.theme=dark index.ipynb
	sed -i .orig \
		's/<title>.*<\/title>/<title>G3 Portfolio \| Modeling and Analysis<\/title>/g' \
		index.html

fix-json:
	jq -M 'del(.metadata.widgets)' results.ipynb \
		> fixed.ipynb

clean:
	rm -f input.ipynb index.html
