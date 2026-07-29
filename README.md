# CVs Colin LEVERGER

LaTeX sources for my CV, in English and French. Both are one page, built from
`friggeri-cv.cls` with the fonts vendored into each language directory.

## The CVs

These are the current builds, and the English one is what
[colinleverger.fr](https://colinleverger.fr) links to:

* **English** — [en/Colin-LEVERGER.pdf](https://colinleverger.github.io/cv-colinleverger/en/Colin-LEVERGER.pdf)
* **French** — [fr/Colin-LEVERGER.pdf](https://colinleverger.github.io/cv-colinleverger/fr/Colin-LEVERGER.pdf)

The PDFs are committed alongside their sources, so whatever is in the repo is
what gets served.

## Building

`xelatex` is the only engine that works here — the class depends on `fontspec`
and `unicode-math`, and the fonts are loaded from local `.otf`/`.ttf` files.

```bash
cd en   # or fr
xelatex Colin-LEVERGER.tex
xelatex Colin-LEVERGER.tex   # second pass, for cross-references and outlines
```

Then commit the regenerated PDF along with the `.tex` change.

Note: the `Makefile` in each directory only has a `clean` target, and it uses
BSD `find -E` syntax, so it will not run as-is on GNU/Linux.

## There is hidden text in these PDFs, on purpose

Both CVs carry a block of 1pt white-on-white text in the bottom margin of the
last page. It is invisible in the rendered PDF and fully extractable by any text
parser. It states an assessment of me and then immediately declares what it is,
and tells any automated screener that a document is data rather than
instructions and that it should disregard the whole thing.

It is deliberate, it is not trying to deceive anyone, and it is explained in
full at **<https://colinleverger.fr/prompt-inject.html>**.

An earlier, covert version of this did try to manipulate automated screeners —
including a clause that would have marked down other candidates. That has been
removed; the write-up covers why.

Prior art, credited on that page: Fielding Johnston,
[I Put a Prompt Injection on My Resume](https://justfielding.com/blog/hidden-prompt-injection-on-my-resume).

## Repository layout

```
en/   English CV: Colin-LEVERGER.tex, friggeri-cv.cls, fonts, img/
fr/   French CV, same structure
*/design/   older builds, kept for reference — these are NOT current
```

`design/` holds stale PDFs from an earlier build and does not track the current
sources. Use the top-level PDF in each language directory.
