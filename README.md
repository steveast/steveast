# Resume — Stepan Maslennikov

One-page static resume in two languages, no build step.

- English: https://steveast.github.io/steveast/ — [Stepan_Maslennikov_CV.pdf](Stepan_Maslennikov_CV.pdf)
- Russian: https://steveast.github.io/steveast/ru/ — [Stepan_Maslennikov_CV_ru.pdf](Stepan_Maslennikov_CV_ru.pdf)

Published by GitHub Pages from the root of `master`. Both pages share `styles/style.css` and `i/`.
Keep their content in sync when editing.

## Local preview

    python3 -m http.server 8000

and open http://localhost:8000 (Russian: http://localhost:8000/ru/).

## Updating the PDFs

The PDFs are the print versions of the pages (see `@media print` in `styles/style.css`):
one column, so ATS parsers read them in order. The English PDF has no photo (US/UK norm),
the Russian one keeps it (`class="print-photo"` on its `<body>`).
Regenerate both after every content change:

    google-chrome-stable --headless --no-pdf-header-footer \
      --print-to-pdf=Stepan_Maslennikov_CV.pdf index.html
    google-chrome-stable --headless --no-pdf-header-footer \
      --print-to-pdf=Stepan_Maslennikov_CV_ru.pdf ru/index.html

Bump `?v=` on the stylesheet link in both pages when the CSS changes.
