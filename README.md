## 5 ways not to upgrade Posit Team

Use the c to make some 🎊!

## Setup 

From a terminal in positron run `quarto install tinytex` and `quarto install chromium` and `quarto add emilhvitfeldt/quarto-revealjs-editable` and `quarto add ArthurData/quarto-confetti` 

Preview it: 
```
cd presentation
quarto render Presentation.qmd
quarto preview Presentation.qmd --no-browser --port 5503
quarto preview Presentation.qmd --no-browser --no-watch-inputs --port 5503

```

View it at `http://localhost:5503/Presentation.html` (or whatever port)

From Positron some tips for quarto: <https://quarto.org/docs/tools/positron/>

Pro tip set width: 1800 and height: 1050 so the text looks reasonably small

## Troubleshooting 

> ERROR: database is locked

See: <https://github.com/quarto-dev/quarto-cli/issues/13006> 

## Quarto Presentations Inspiration

Presentations: <https://quarto.org/docs/presentations/>

Quarto is fun: <https://quartoisfun.com/slideshows/example.html#/title-slide> 

Quarto slides template: <https://github.com/sebastiandres/quarto_slides_template> 

Beautiful reports and presentation with Quarto by Tom Mock: <https://thomasmock.quarto.pub/reports-presentations/#/title-slide> 

Magical extension for editing presentations: <https://github.com/EmilHvitfeldt/quarto-revealjs-editable> 

Make some confetti: <https://github.com/ArthurData/quarto-confetti#readme> 

Reveal themes: <https://quarto.org/docs/presentations/revealjs/themes.html> 

[Lisa's renv Presentation](https://questionable.quarto.pub/reproduceable-workflows/) ([code](https://github.com/leesahanders/demo_renv))

[David's renv presentation](https://github.com/edavidaja/you-should-use-renv)

[Katie's API talk](https://github.com/kmasiello/getting-started-apis)

[Ralf's presentation](https://github.com/rstub/neues_in_r) ([code](https://rstub.quarto.pub/neue-entwicklungen-in-r/))

[Katie's Posit conf 2025 slides](https://github.com/kmasiello/positconf2025_slidetemplate) 

[Official Posit slides](https://github.com/posit-dev/positslides) 


Long term consider moving it to scrollytelly: <https://posit.co/blog/closeread-prize-winners> 

More slide deck resources: 

- https://posit-dev.github.io/posit-slides/
- https://positpbc.atlassian.net/browse/BRAND-2801
- https://github.com/posit-dev/positthemes
- https://github.com/posit-dev/positslides
- https://positpbc.atlassian.net/wiki/spaces/MAR/pages/85983233/Posit+Brand+Assets+Style+Guide
- https://posit-dev.github.io/brand-yml/inspiration/brand-guidelines/posit/
- https://posit-dev.github.io/brand-yml/inspiration/
- https://posit-dev.github.io/brand-yml/
- https://github.com/posit-dev/positslides
- https://connect.posit.it/service-accounts-in-connect/#/title-slide
- https://github.com/leesahanders/server-hardening-for-kx/blob/main/presentation/night.scss



