# pandoc-defaults

This is a personal collection of defaults files for pandoc (specified via the `-d` switch).

## Files for roff ms output

`ms.yaml` and companions is a set of defaults files for (g)roff ms output, primarily for PDF. It assumes the presence of the lua filters listed in `ms.yaml`, as well as the template `bk.ms`.

Aside from the main file, the following additional defaults for `ms` are currently present:

- `ms/div`: Filtering settings for fenced divs, by class and by attribute (such as `lang`).

- `ms/toc`: Adds a table of contents to the end of the document.

- `ms/coverpage`: Adds a table of contents and renders a title page (instead of a title/author section at the top of the first page).

- Font (family, pointsize, lineheight) settings under `ms/fonts/`:
  - `als`: Alegreya Sans.
  - `cm`: New Computer Modern Serif + New Computer Modern Sans (for headings).
  - `cr`: Crimson Text.
  - `gar`: EB Garamond + FiraGO.
  - `garlib`: Garamond Libre + FiraGO.
  - `lf`: Libertinus + FiraGO.
  - `lora`: Lora.
  - `mm`: Minion + Myriad.
  - `ss`: Source Serif + Source Sans.
  - `t`: Free Serif (a Times-like font, hence the abbreviation).

Typical usage:

```sh
pandoc -d ms -d ms/div -d ms/fonts/gar -o my.pdf my.md
```
