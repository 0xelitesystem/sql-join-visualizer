# SQL Join Visualizer

An interactive teaching tool for SQL joins. Pick INNER, LEFT, RIGHT, FULL OUTER, or CROSS JOIN and see three things update together: a Venn diagram of what the join keeps, the generated SQL statement, and the actual result table computed live from editable sample data. Single HTML file, no external dependencies, works offline.

## Live demo

https://0xelitesystem.github.io/sql-join-visualizer/

## Features

- Five join types: INNER, LEFT, RIGHT, FULL OUTER, CROSS
- Inline SVG Venn diagram that highlights exactly which regions the selected join keeps
- The generated SQL statement for each join, with keyword highlighting
- A result table computed by real join logic in the browser, not hardcoded output
- Editable sample tables: change any cell, add or remove rows, and the result recomputes instantly
- NULLs rendered where a side has no match, with unmatched rows visually flagged
- One-line plain-language explanation per join type
- Sample data deliberately includes a user with no orders and an order pointing at a missing user, so the difference between join types is visible immediately
- Light and dark theme toggle, keyboard-usable controls

## How it works

The two sample tables (`users` and `orders`) live in editable HTML cells. On every edit the tool reads the current rows back out of the DOM and runs a small join engine written in plain JavaScript: for INNER it emits only key-matched pairs, for LEFT it also emits left rows with no match padded with NULLs, for RIGHT it walks the orders side the same way, FULL OUTER unions both behaviors, and CROSS emits every pairing with no key at all. The Venn diagram is drawn inline with SVG masks and clip paths, so region highlighting is just a class toggle.

## Privacy

Everything runs client-side in your browser. Nothing you type leaves the page, no requests are made, no analytics, no cookies. You can open DevTools and watch the network tab to confirm.

## More

Part of a catalog of single-file browser tools and plain-language references, all MIT licensed and dependency-free: [0xelitesystem.github.io](https://0xelitesystem.github.io/). Built by [elitesystem.ai](https://elitesystem.ai).

## License

MIT. Copyright 0xelitesystem 2026.
