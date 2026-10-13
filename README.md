# Futures Compass

Futures Compass walks a team through design-forward scenario planning in five stages: define a domain, rank the driving forces, draft four futures, propose concepts, and sort them into a strategy board. Claude does the legwork at each stage and you review and steer before anything advances. Each future can get a simple drawn picture and each concept a black-and-white sketch, each stage can be exported as a discussion deck, and a transcript of the group's conversation can be summarized into steering notes for the next stage.

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

## Pictures and sketches

The visuals are deliberately simple. Claude can't paint pixels, so it **draws vector art (SVG) as code**: one flat, poster-style scene per future (locked to the app's color palette) and one black-and-white napkin sketch per concept, with a slight hand-drawn wobble. Expect bold shapes, rough wireframes, and diagrams, not photographs or polished illustration, and expect quality to vary from run to run. Each picture has a Redraw button. Drivers get no images. The drawings are cleaned before they are shown (scripts, external references, and off-palette colors are stripped), and they are included in the exported decks.

**No image key is needed.** The drawings use the same Claude access as the rest of the page, so there's nothing to configure and nothing to leak.

### Going further: photographic images from OpenAI or Gemini

You can swap in real image-model output, but it isn't a setting you can flip in the Artifact version. The page runs inside claude.ai's sandbox, which blocks calls to outside services, so an image provider can't be reached from there. The path is:

1. Run the page outside the Artifact sandbox (for example as a small standalone web app), where calls to other services are allowed.
2. Have each person enter their own OpenAI or Gemini API key in the browser. Keep the key in the browser's local storage or an untracked `.env` file, never in the repo (`.gitignore` already excludes `.env*`).
3. Replace the drawing step with a request to the image provider's API. In `index.html` that is `drawBatch`, which calls Claude with the prompts from `buildFutureImagePrompt` and `buildSketchPrompt` and stores the cleaned SVG. Store the returned image instead, and show it where the SVG is shown now.

Depending on the provider, a small proxy may be needed because some image APIs don't accept direct browser calls. Image-model calls are billed to the key's owner, so each person would pay their own provider as well as their own Claude usage. This is a sketch of the approach, not something already built or tested here.

## Cost and privacy

- **Usage is billed to whoever is running it.** Each Claude call the page makes (researching drivers, drafting futures, drawing a picture or sketch, summarizing a transcript) counts against the signed-in viewer's own Claude usage, not the author's. A full run, pictures included, is roughly 15 calls.
- Your progress is saved only in your browser's local storage. Exported decks and transcripts stay on your machine.
- The page loads fonts from Google Fonts and the deck builder (PptxGenJS) from jsDelivr.

## Files

- `index.html`: the whole app, a single self-contained file.
- `LICENSE`: MIT.
