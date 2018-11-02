# papers-ieee
LaTeX Templates and drafts of misc papers for IEEE

See also:

* [LaTeX templates instructions](http://www.ctan.org/tex-archive/macros/latex/contrib/IEEEtran/IEEEtran_HOWTO.pdf)
* [Template source](https://www.ieee.org/content/dam/ieee-org/ieee/web/org/conferences/Conference-LaTeX-template_7-9-18.zip) -
  it is also stored in `./examples`.

# build steps

Debian OS family:

```
# apt install texlive-science texlive-latex-base
# pdflatex foo.tex
```

# live edit a paper
===================

```
# docker run --rm -it -v $(pwd):/home danteev/texlive:TL2017 latexmk foo.tex
```

Beware, it gets quite a fat image of a 6G, it may be faster for you to build it
locally by hand:
```
# git clone https://github.com/dante-ev/docker-texlive
# cd docker-texlive
# docker build .
```
