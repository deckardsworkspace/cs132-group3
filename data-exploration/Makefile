all: convert

convert: execute to-html
from-colab: execute-colab to-html

execute:
	python -m jupyter nbconvert --inplace --execute \
		--output index cs132_data_exploration.ipynb

execute-colab: fix-json
	python -m jupyter nbconvert --inplace --execute \
		--output index fixed.ipynb

to-html:
	python -m jupyter nbconvert --to html \
		--output index index.ipynb

fix-json:
	jq -M 'del(.metadata.widgets)' cs132_data_exploration.ipynb \
		> fixed.ipynb

clean:
	rm -f input.ipynb index.html
