# Prompt Recipes

Use these recipes for Chinese typographic meme posters. Keep prompts short and precise.

## Base Poster Prompt

```text
Use case: ads-marketing
Asset type: vertical meme poster, 2:3 portrait
Primary request: Create a typographic Chinese internet-culture poster matching the provided reference style: oversized Chinese block characters, dense stacked layout, high contrast, gritty worn print texture.
Text (verbatim): "<CHINESE_TEXT>"
Small English accent text (verbatim): "<ENGLISH_ACCENT>"
Style/medium: bold street poster, distressed ink, vintage screenprint, Chinese typography as the main visual subject.
Composition/framing: portrait poster, huge readable Chinese characters filling most of the frame, one small accent label, minimal illustration.
Color palette: <PALETTE>
Constraints: The Chinese text must be exactly "<CHINESE_TEXT>" and readable. No watermark, no logo, no extra Chinese text, no unrelated illustration.
```

## Color Variants

- Reference-like red/black: `off-white paper, black ink, punchy red label, white accent text`
- Black/yellow meme: `black background, warm yellow Chinese characters, white accent text, tiny red stamp`
- Editorial concept: `cream paper, black typography, deep red horizontal bar, subtle worn scratches`

## Four-Character Accuracy Prompt

Use when the headline is exactly four Chinese characters or when a prior result misrenders text.

```text
Create a typographic Chinese poster with EXACTLY FOUR large Chinese characters only.
Text (verbatim): "<TEXT>"
Arrange the four characters as a 2x2 grid: <C1> <C2> / <C3> <C4>.
The only Chinese text must be exactly "<TEXT>". Do not add any other Chinese characters.
Make every character readable.
```

## Topic Plan Template

```text
1. <Chinese phrase> | <English accent> | <filename-slug> | <palette>
2. ...
```

## Quality Checklist

- Main Chinese headline is readable.
- No unexpected extra Chinese words.
- Poster resembles the reference assets in typography, palette, and texture.
- No watermark or logo.
- Saved in the requested project folder.
