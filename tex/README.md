If you're looking for the PDF, you're lost, go back to the root! 

If you're sufficiently nerdy enough to want to compile someone else's LaTeX paper on your own machine, you're in the right place.

## Compiling Locally

Compiling locally is possible with any LaTeX distribution; the github actions [workflow](https://github.com/LKedward/latex-github-collab/blob/master/.github/workflows/CI.yml) (Ubuntu 20.04) uses the following packages (all installable via `apt`):

- `texlive-latex-recommended`
- `texlive-latex-extra`
- `texlive-extra-utils` (_optional:_ needed for `texcount`)
- [`rubber`](https://gitlab.com/latex-rubber/rubber/) (_optional:_ needed for Makefile usage)
- `perl` (_optional:_ needed for texcount and latexdiff)
- `latexdiff`(_optional_)

For running the spellcheck, the following packages are required:

- [`textidote`](https://github.com/sylvainhalle/textidote/releases/tag/v0.8.2) (for generating plain-text from tex)
- `codespell` (installable with `pip3`)

For convenience a Makefile is included which relies on the [rubber](https://gitlab.com/latex-rubber/rubber/) LaTeX wrapper.


If you are in the repo root (`cd ..`), you can run the following commands on your command line to perform the following actions:
```
$ make             # generate paper.pdf
$ make clean       # cleanup
$ make spellcheck  # run codespell
$ make count       # run TexCount
$ make diff        # run latexdiff with master
```

