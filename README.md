# An emdash site and opencode in a browser tab

An [emdash](https://www.npmjs.com/package/create-emdash) site made with Bun and served by `bun dev`, with opencode beside it, in [elette](https://elette.dev/): a Linux machine in your browser tab. Nothing is installed on your computer.

**Open it:** https://elette.dev/?import_gh=rbbydotdev/elette-emdash-demo

elette clones this repository into a new project and opens three panes:

| Pane | What it runs |
|---|---|
| server | `egg pkg install bun`, `bun create emdash@latest site --yes` the first time, then `bun dev` in `site/` |
| opencode | `egg pkg install opencode && opencode`: the coding agent, in this project |
| preview | the site on port 4321 |

The first start makes the site and installs its packages, which takes a few minutes. Edit the site in the editor or ask opencode to; the dev server reloads the preview.

## Make your own

The panes are files in `.egg/autostart/`, one [XDG autostart](https://specifications.freedesktop.org/autostart-spec/latest/) entry per pane, started in name order:

- A terminal pane: `Terminal=true` and the command in `Exec`.
- A preview pane: `X-Eggshell-Preview=PORT/PATH`.
- A file pane: `X-Eggshell-File=PATH`.

The layout, files, opencode and preview side by side with the terminal below, is `.egg/config.json`: arrange the panes, then Views, Save layout writes it.
