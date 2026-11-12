# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

Static HTML/CSS/JS in a single `index.html`, no build step and no framework. Deployed with GitHub Pages (workflow in `.github/workflows/static.yml`).

## Users

General public in Brazil who want to plan vacations or time off: they enter one or more periods and see how those periods fall against weekends and national holidays.

## Product Purpose

Let anyone plan periods of time off on a yearly calendar, counting calendar days (weekends included), and see at a glance which holidays fall before, inside or right after each period. Success means the person settles on dates and can share them easily.

## Positioning

Two things weigh equally:
- Periods defined either by a fixed end date or by a number of calendar days (start day counts as day 1), shown against Brazilian holidays computed for any year, including movable ones (Carnaval, Sexta-feira Santa, Corpus Christi).
- A clean, shareable PNG of the planned periods (only the months from the first to the last period), plus JSON import/export to move periods between devices or people.

## Operating Context

Used in the browser on desktop and phone. People share the result by sending the exported PNG (to a manager, family) or the JSON file. Language: Brazilian Portuguese.

## Capabilities and Constraints

- Multiple periods, each with start date and either "Qtd. dias" or "Data fim"; each period gets its own color.
- Full-year view with year paging (buttons and arrow keys).
- National holidays: fixed dates plus Easter-based ones; Consciência Negra only from 2024. Carnaval, Quarta de Cinzas and Corpus Christi are labeled ponto facultativo.
- Import/export periods as JSON; export PNG via canvas.
- No server: data lives only in the viewer's browser (localStorage). Sharing happens through files.
- Must work well on mobile.
- State and municipal holidays: only São Paulo so far (state holiday 9 July; city holidays 25 January and Corpus Christi), chosen in a "Feriados considerados" selector; they count as days off like national ones.
- No example periods on first load: the page starts empty.

## Evidence on Hand

No testimonials, usage data or brand assets exist. Do not fabricate them.

## Product Principles

1. Dates must be correct: holiday rules and day counts are the product's credibility.
2. Zero setup: open the page and use it, no account, no server.
3. Sharing is a first-class outcome: what's on screen should export cleanly.
4. Works on a phone as well as on desktop.

## Accessibility & Inclusion

No product-specific requirement established beyond keyboard-operable controls and readable contrast in light and dark themes.
