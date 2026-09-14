# Personal research site — FIXED VERSION (2026-09-14)

This replaces any earlier copy of index.html you may have. The version
you had before still contained placeholder "#" links for Paper, Code,
GitHub, Google Scholar, and Email — that's why clicking them just
scrolled to the top of the page.

## Verify before you deploy

Run this in the folder before pushing, to confirm you have the right file:

    grep -c 'href="#"' index.html

This MUST return 0. If it returns anything higher than 0, you still have
the stale version — do not push it.

## Deploy

    cd ~/github/site
    cp /path/to/this/index.html .
    cp /path/to/this/spy_momentum.js .
    grep -c 'href="#"' index.html        # confirm 0 before proceeding
    git add index.html spy_momentum.js
    git commit -m "Fix: replace placeholder links with live SSRN/GitHub URLs"
    git push

GitHub Pages rebuilds automatically within a minute or two of the push.
