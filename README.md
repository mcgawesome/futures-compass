# Futures Compass

Futures Compass walks a team through design-forward scenario planning in five stages: define a domain, rank the driving forces, draft four futures, propose concepts, and sort them into a strategy board. Claude does the legwork at each stage and you review and steer before anything advances; each stage can also be exported as a discussion deck, and a transcript of the group's conversation can be summarized into steering notes for the next stage.

## What you need

- Claude Code installed (the desktop app's Code tab, which can publish Artifacts) and signed in with **your own** Claude account.
- Nothing from the author is shared: no keys, no accounts, no data.

## Setup

1. Clone the repo: `git clone <repo-url>`
2. Move into it: `cd futures-compass`
3. Start Claude Code: `claude`

## Sample first prompt

> Publish `index.html` as an Artifact exactly as it is, without changing the code. Enable the `sample` and `downloads` capabilities, and give it the title "Futures Compass". Then give me the link.

Open the link it returns. The page opens with a prefilled example (a restaurant group planning for the next few years). Edit it or clear it, then click **Continue to drivers**.

If your version of Claude Code can't publish Artifacts, paste the contents of `index.html` into a claude.ai chat and ask for the same thing.

## Cost and privacy

- **Usage is billed to whoever is running it.** Each Claude call the page makes (researching drivers, drafting futures, summarizing a transcript) counts against the signed-in viewer's own Claude usage, not the author's.
- Your progress is saved only in your browser's local storage. Exported decks and transcripts stay on your machine.
- The page loads fonts from Google Fonts and the deck builder (PptxGenJS) from jsDelivr.

## Files

- `index.html`: the whole app, a single self-contained file.
- `LICENSE`: MIT.
