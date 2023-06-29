# sed -i works differently on Darwin, so we have to handle it manually
SED_FLAGS := --in-place=.orig
ifneq ($(OS),Windows_NT)
	UNAME_S := $(shell uname -s)
	ifeq ($(UNAME_S),Darwin)
		SED_FLAGS := -i .orig
	endif
endif

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
		--output modeling_analysis --HTMLExporter.theme=dark index.ipynb
	sed $(SED_FLAGS) \
		's/<title>.*<\/title>/<title>G3 Portfolio \| Modeling and Analysis<\/title>/g' \
		modeling_analysis.html

fix-json:
	jq -M 'del(.metadata.widgets)' results.ipynb \
		> fixed.ipynb

clean:
	rm -f input.ipynb index.html
