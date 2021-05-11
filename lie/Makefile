TARGET ?= presentation.html

presentation: presentation.md
	pandoc --verbose -t revealjs --mathjax -s --self-contained -i -o ${TARGET} presentation.md -V revealjs-url=./assets/reveal.js

.PHONY : clean

clean:
	rm -f ${TARGET}
