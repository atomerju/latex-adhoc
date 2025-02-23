DK_LABEL := atomerju/latex

LATEX_FILE := input.tex

build-image:
	docker build -t $(DK_LABEL) .

build:
	docker run --rm -i -v "$$PWD":/data $(DK_LABEL) pdflatex $(LATEX_FILE)
