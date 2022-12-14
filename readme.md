# pandoc-defaults

A personal collection of defaults files for pandoc (specified via the `-d` switch).

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
  - `plain`: Times + Helvetica ("native" fonts T and H)
  - `pal`: Palatino + Avant Garde ("native" fonts P and A)
  - `ss`: Source Serif + Source Sans.
  - `t`: Free Serif (a Times-like font, hence the abbreviation).

Typical usage:

```sh
pandoc -d ms -d ms/div -d ms/fonts/gar -o my.pdf my.md
```

## Files for LaTeX output

`xe.yaml` and companions is a set of default files for LaTeX/PDF output using XeLaTex. The files in the `xe/` directory are font settings, named by short mnemonic. Currently these are:

- `cam`: Cambria + Source Sans
- `caslon`: Caslon + Futura
- `cm`: New Computer Modern Serif + Sans
- `crim`: Crimson Pro + Alegreya Sans
- `gar`: EB Garamond + FiraGO.
- `mm`: Minion + Myriad
- `pal`: Palatino + Avant Garde
- `pt`: PT Serif + PT Sans
- `sabon`: Sabon + Futura

Typical usage:

```sh
pandoc -d xe -d xe/gar -o my.pdf my.md
```

The default fontsize is 11pt; to change this set the `fontsize` variable.
