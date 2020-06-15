# hugo-academic-unsw-slides
UNSW Slide theme for Hugo Academic

Note that Hugo Academic slides is using [Reveal.js](https://revealjs.com/). 
If you want a UNSW slide theme for Reveal.js, and not just for Hugo Academic slides, this slide theme is a good place to start.

# Quick Installation
1. Require Hugo Academic v4.8
1. Download this folder to `<your-hugo-acad-dir>\content\slides`
1. If you are running hugo locally, you may access the slides via `http://localhost:1313/slides/hugo-academic-unsw-slides/#/`. Also see [sample demo](https://www.lukesy.net/slides/hugo-academic-unsw-slides).

# Advance Features
1. Look at the sample code `advance-sample.md` for slightly more advanced features (e.g., multi column, fragments/slide transitions). A rendering of this (advanced) sample code can be found [here (it is also my EMBC presentation)](https://www.lukesy.net/slides/embc2020-ckfdist/#/).
1. To enable Reveal.js' slide numbering feature (assuming my [pull request](https://github.com/gcushen/hugo-academic/pull/1744) are not accepted in hugo-academic), update the following files (you might need to diff it if hugo-academic has updated).
   1. `advance\baseof.html` to `themes\academic\layouts\slides\baseof.html`. I basically added `slide_number` (and `vert_centering` which will not work w/ the unse theme) parameters to `revealDefaults`. 
   1. `advance\index.md_` to `<your-hugo-acad-dir>themes\academic\archetypes\slides\index.md`. Note that you'll have to rename the file extension. This updates the template slides when you use `hugo new --kind slides` command.