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

| Web address | Comes from | Published? |
|---|---|---|
| `/set1/` | `practice_sets\Set1\Unit1_Practice_Set.html` | Yes |
| `/set2/` | `practice_sets\Set2\Unit2_Practice_Set.html` | No — draft |
| `/set3/` | `practice_sets\Set3\Unit3_Practice_Set.html` | No — draft |
| `/set4/` | `practice_sets\Set4\Unit4_Practice_Set.html` | No — draft |
| `/set5/` | `practice_sets\Set5\Unit5_Practice_Set.html` | No — draft |
| `/set6/` | `practice_sets\Set6\Unit6_Practice_Set.html` | No — draft |

All six sets exist in Dropbox, but only the ones marked published are on the web. The rest show as
greyed placeholders on the landing page and their URLs return 404. `publish.bat` has a line for each
set; the unpublished ones are commented out with `REM`.

## What must never be committed here

This repository is public. The Connect PDFs are McGraw-Hill copyrighted material and stay in Dropbox
only. So do quizzes, exams, answer keys and slide decks. `.gitignore` blocks `Connect/` and every
`.pdf`, `.docx`, `.pptx`, `.xlsx`, `.csv` and `.tex` as a second line of defence, but the real
safeguard is that `publish.bat` copies named HTML files and nothing else.

The practice sets themselves are safe to publish. They are ungraded, they show their own worked
solutions on purpose, and they contain no quiz or exam material.

## Publishing a set

1. Verify it in Dropbox (`verify\check.bat`).
2. Delete the `REM ` from that set's `call :put` line in `publish.bat`.
3. In `index.html` here, change that set from a greyed `<span class="soon">` placeholder to a real
   link, following the pattern of Quiz 1, and fill in its topics and dates.
4. Run `publish.bat`.

To unpublish, reverse steps 2 and 3, delete the set's folder from this repository, and run
`publish.bat` again.

## Notes

- `robots.txt` disallows all crawlers and each page carries a `noindex` tag, so the site should stay
  out of search results. The URLs are still public to anyone who has them.
- `.nojekyll` turns off Jekyll processing; these are plain static files.
- Each practice set is entirely self-contained: no external CSS, JavaScript, fonts or images. Once a
  page has loaded it works offline.
