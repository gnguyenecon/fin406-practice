# FIN 406 practice sets

Public web hosting for the FIN 406 self-checking practice sets, so students can click a link in
Canvas and have the page run immediately. Canvas will not execute JavaScript in an uploaded HTML
file, and Dropbox serves HTML as a download rather than rendering it; GitHub Pages serves the files
as ordinary web pages.

Live site: <https://gnguyenecon.github.io/fin406-practice/>

## This repository is published output, not the source

The editable files live in Dropbox:

```
Dropbox\PennState\Teaching\FIN406_FA2026\practice_sets\
```

Edit them there, verify them there, then run `publish.bat` in that folder. It copies the HTML into
this repository and pushes. Editing a file here directly will be overwritten on the next publish.

| Web address | Comes from |
|---|---|
| `/set1/` | `practice_sets\Set1\Unit1_Practice_Set.html` |
| `/set2/` | `practice_sets\Set2\Unit2_Practice_Set.html` |

## What must never be committed here

This repository is public. The Connect PDFs are McGraw-Hill copyrighted material and stay in Dropbox
only. So do quizzes, exams, answer keys and slide decks. `.gitignore` blocks `Connect/` and every
`.pdf`, `.docx`, `.pptx`, `.xlsx`, `.csv` and `.tex` as a second line of defence, but the real
safeguard is that `publish.bat` copies named HTML files and nothing else.

The practice sets themselves are safe to publish. They are ungraded, they show their own worked
solutions on purpose, and they contain no quiz or exam material.

## Adding a new set

1. Build and verify the new set in Dropbox as usual (`verify\check.bat`).
2. Add one `call :put` line to `publish.bat`, following the pattern of the existing two.
3. Add the set to the list in `index.html` here.
4. Run `publish.bat`.

## Notes

- `robots.txt` disallows all crawlers and each page carries a `noindex` tag, so the site should stay
  out of search results. The URLs are still public to anyone who has them.
- `.nojekyll` turns off Jekyll processing; these are plain static files.
- Each practice set is entirely self-contained: no external CSS, JavaScript, fonts or images. Once a
  page has loaded it works offline.
