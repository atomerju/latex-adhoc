DK_LABEL := atomerju/latex
DK_IMG_ID = $(shell docker images | grep atomerju/latex | awk '{print $$3}')

LATEX_FILE := input.tex

image-id:
	@echo "Image Id: $(DK_IMG_ID)"

build-image:
	if [[ ! -z "$(DK_IMG_ID)" ]]; then docker rmi $(DK_IMG_ID); fi
	docker build -t $(DK_LABEL) .

build-pdflatex:
	docker run --rm -i -v "$$PWD":/data $(DK_LABEL) pdflatex $(LATEX_FILE)

build-luatex:
	docker run --rm -i -v "$$PWD":/data $(DK_LABEL) lualatex $(LATEX_FILE)
