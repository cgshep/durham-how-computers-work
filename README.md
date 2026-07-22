# How a Computer Really Works

A single-page, interactive taster session for **Destination Durham**, Durham University's
widening participation scheme. It runs school students from "a computer is just switches"
through binary, the fetch–decode–execute cycle, and hands-on activities with a real
RISC-V emulator ([RV32 Workbench](https://cs.gl/riscv-web-emulator/)).

Written and delivered by Dr Carlton Shepherd (Durham University / Newcastle University).

## Structure

```
index.html          The whole page (content, styles, and interactive widgets)
assets/fonts/        Libre Baskerville woff2 files used for headings
assets/img/          Favicon and host photo
```

The page is a single static HTML file with no build step and no external
dependencies at runtime (fonts and images are all local, so it works offline
in a session room with no wifi).

## Previewing locally

Any static file server works, e.g.:

```
python3 -m http.server 8000
```

then open `http://localhost:8000/`.

## Updating content

All section content lives directly in `index.html`, split into `<section>`
blocks with clear `<!-- ==== NAME ==== -->` comments (e.g. `THE PLAN`,
`BINARY`, `ACTIVITIES`, `WORKBOOK`). Styling is in the single `<style>` block
at the top; interactive widgets (the bit-flipper, the ASCII chips, the
decimal→binary converter) are in the `<script>` block at the bottom.

To swap the host photo, replace `assets/img/carlton-shepherd.jpg` and keep
the same filename, or update the `src` in the `#host` section and the
`og:image` meta tag in `<head>`.
