---
name: meme-poster-generator
description: Generate Chinese internet meme or hot-topic typographic posters from reference images. Use when the user asks to find Chinese trending opinions, buzzwords, memes, puns, homophones, or hot search topics, then generate poster-like bitmap images in the style of local reference assets and save them to an output folder.
---

# Meme Poster Generator

Create a batch of Chinese internet-culture posters where typography is the main visual subject. This skill is optimized for workflows like: inspect `asset/` images, choose current Chinese hot memes or debated concepts, generate similar vertical posters, and save final images into `out/`.

## Workflow

1. Inspect local references first.
   - Look for `asset/`, `assets/`, or a user-named reference folder.
   - Use `Get-ChildItem`/`rg --files` to list image files.
   - Use `view_image` on 2-4 representative images and summarize the visual system: aspect ratio, dominant colors, typography, texture, layout density, and whether text or illustration is primary.

2. Gather Chinese topic candidates.
   - If the user asks for latest, current, today, top, hot, or recent topics, browse the web and prefer Chinese sources, hot-search pages, official annual word lists, encyclopedia pages, or media roundups.
   - Mix two types when appropriate: internet memes/puns and broader debated concepts.
   - Avoid unsafe, defamatory, private-person, explicit, or politically sensitive slogans unless the user explicitly provides them and the request is allowed.
   - Keep the final list concise, usually 10 items unless the user specifies another count.

3. Create a generation plan.
   - For each item, choose: Chinese text, optional short English accent text, filename slug, and color variant.
   - Preserve the reference style rather than inventing an unrelated illustration style.
   - Prefer large readable Chinese typography, rough ink/screenprint texture, simple high-contrast palettes, and minimal iconography.

4. Generate with the built-in `image_gen` tool by default.
   - Use one tool call per distinct poster.
   - Treat local images as style references, not edit targets, unless the user asks to modify a specific image.
   - If the user requested a project output folder, copy each generated image from `$CODEX_HOME/generated_images/...` into that folder. Leave originals in place.
   - Do not switch to CLI/API image generation unless the user explicitly asks for it.

5. Validate and iterate.
   - Open representative outputs with `view_image`.
   - Check that the main Chinese text is readable and close to the intended phrase.
   - Regenerate any poster with incorrect Chinese, extra slogans, weak resemblance to the reference, or obvious watermarks/logos.
   - Verify final files are valid images and share a consistent aspect ratio.

6. Report results.
   - Provide the output folder and filenames.
   - Include the chosen topics and note any sources used for current topics.
   - Mention validation results such as image count and dimensions.

## Topic Selection

Use Chinese terms that can work as poster headlines. Good candidates are short, punchy, and visually legible:

- 2-6 Chinese characters for the main headline.
- Memes, homophones, ironic phrases, or topic labels with clear cultural currency.
- Broad concepts that people discuss online, such as work pressure, emotional value, AI, consumption, entertainment, or identity.

For current-topic requests, browse before deciding. For evergreen or offline requests, use the user-provided topic list or generate a plausible list and label it as inferred.

## Prompting

Read `references/prompt-recipes.md` when writing generation prompts. Use its base prompt and color variants, then fill in the exact phrase.

Prompt rules:

- Specify the exact Chinese text in quotes.
- Tell the model the Chinese text must be readable and must not include extra Chinese text.
- Use short English accent copy only as decorative support.
- Ask for no people, no mascot, no logo, no watermark, and no unrelated illustration unless the reference images clearly use those elements.
- When text accuracy matters, prefer a simple layout such as four huge characters in a 2x2 grid.

## Output Conventions

Default to:

- Reference folder: `asset/`
- Output folder: `out/`
- Format: PNG
- Aspect ratio: vertical 2:3 when the references are poster-like
- Filenames: `01-slug.png`, `02-slug.png`, etc.

Create the output folder if needed. Do not overwrite unrelated files unless the user explicitly requests replacement.
