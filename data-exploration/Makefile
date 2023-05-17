all: convert

convert:
	python -m jupyter nbconvert --to html \
		--output index cs132_data_exploration.ipynb

from-colab: fix-json
	python -m jupyter nbconvert --to html \
		--output index input.ipynb

fix-json:
	jq -M 'del(.metadata.widgets)' cs132_data_exploration.ipynb \
		> input.ipynb

clean:
	rm -f input.ipynb index.html
