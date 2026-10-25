# Land ownership in China

A short terminal presentation for rabbitholeathon. Edit `workshop/slides.md`.
The deck uses Presenterm 0.16.1 with the `terminal-dark` theme and warm heading
colors, matching the setup from `vercel-ship-2026-workers`.

## Present in iTerm without Zellij

Open a new iTerm window or tab on this Mac and run:

```sh
cd /Users/emmaguo/Documents/ChatGPT/rabbitholeathon
mise run workshop:present
```

This launches Presenterm directly in that terminal. Zellij is optional.
Resize the window to at least 120 columns by 40 rows before starting.
Use iTerm's full-screen mode and adjust the font size for the audience.

To preview with automatic reload when you save your Markdown edits:

```sh
mise run workshop:preview
```

The presentation command enables overflow checks. If text does not fit,
enlarge the terminal or reduce the font size, then run it again.

## Set up on another Mac

Copy or clone this repository onto the other Mac. With Homebrew already
installed, install Mise:

```sh
brew install mise
```

Open iTerm in the copied repository folder, then run:

```sh
mise install
mise run workshop:present
```

`mise install` installs the exact Presenterm version recorded in `mise.toml`.
These commands do not require Mise shell activation, Zellij, Node.js, or npm.
If you installed Mise using its own installer and `mise` is not found, use
`~/.local/bin/mise` in place of `mise`.

See [Mise installation](https://mise.jdx.dev/installing-mise.html) and
[getting started](https://mise.jdx.dev/getting-started) for other setup options.

## Run Presenterm directly

From the repository folder, the equivalent presentation command is:

```sh
mise exec -- presenterm --theme terminal-dark --present --validate-overflows workshop/slides.md
```

If Presenterm is already available directly on your terminal's PATH:

```sh
presenterm --theme terminal-dark --present --validate-overflows workshop/slides.md
```

## Controls and editing

- `Space`, `l`, or right arrow: advance, including incremental reveals.
- `h` or left arrow: go back.
- `Ctrl-p`: open the slide index.
- `?`: show key bindings.
- `q`: quit Presenterm and return to the shell.

In the Markdown:

- `<!-- end_slide -->` starts a new slide.
- `<!-- pause -->` reveals the next part on the next advance.
- `<!-- speaker_note: "Your note here" -->` adds a presenter note. Quote notes
  that contain colons.
- Triple-backtick `text` blocks preserve diagram spacing.
- The YAML block at the top controls the title, author, and theme.

## Optional Zellij workspace

On the original Mac, with Zellij installed:

```sh
cd /Users/emmaguo/Documents/ChatGPT/rabbitholeathon
zellij --new-session-with-layout workshop.kdl --session rabbitholeathon
```

This opens stacked editor, slides, and shell panes. The layout uses the original
Mac's Mise path, `/Users/emmaguo/.local/bin/mise`; update that path in
`workshop.kdl` if you want to use this optional layout on another computer.
