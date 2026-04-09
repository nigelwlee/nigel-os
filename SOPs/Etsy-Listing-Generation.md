# Etsy Listing Generation

> Repeatable process for creating and publishing Sleepy Studios SVG card listings on Etsy.

---

## Purpose

Generate consistent, high-quality Etsy listings for Cricut SVG card templates. Covers design specs, copy generation, and publishing.

## Trigger

Manual — each time a new card design is ready for listing.

## Steps

1. **Design in Affinity Designer**
   - Create SVG at 5x7 card dimensions
   - Ensure Cricut compatibility (clean paths, no embedded rasters)
   - Export SVG + preview PNG (transparent where needed)

2. **Generate listing copy via Claude**
   - Use Claude Project template (uuid: `019c1334`)
   - Provide: card name, concept, difficulty (1–5), any special assembly notes

3. **Title format**
   - Pipe-separated (|)
   - Max 140 characters
   - Must end with "(Digital Download)"
   - Example: `Party Hat Birthday Card | SVG Cut File | Cricut | 5x7 Greeting Card (Digital Download)`

4. **Tags**
   - Max 20 characters each
   - No numbering
   - Include: card type, occasion, cut method, tool compatibility

5. **Description**
   - Assembly instructions as text (not PDF)
   - Standard specs block:
     - 216gsm / 80lb cardstock
     - Basic cut
     - 5x7 card size
   - Difficulty rating (1–5)

6. **Publish on Etsy**
   - Upload SVG + preview images
   - Set as Digital Download
   - Assign to appropriate Sleepy Studios section

## Verification

- Listing preview renders correctly on Etsy
- Title under 140 chars
- All tags under 20 chars
- Assembly instructions are clear without visual aids

## Troubleshooting

- **SVG not cutting correctly:** Check for open paths in Affinity Designer
- **Claude output too generic:** Add specificity to the card concept in the prompt
- **Tags truncated:** Etsy silently truncates tags over 20 chars — verify in listing editor

---

> See also: [[Projects/MY-SSTU/_Briefing-my-sstu|Sleepy Studios]] | [[SOPs/_Map-sops|SOPs]]
