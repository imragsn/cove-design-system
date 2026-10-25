# COVE — Shapes and non-destructive image masks

06 / COVE SYSTEM

A shape is a contract.

Geometry must be reproducible across HTML, SVG and editable slide tools.

 | ID / shape | Geometry at 1920 x 1080 | Purpose and limits

 | S01 / Soft panel | Rectangle, all corners r32; 40 px padding; 24 px gap | Default text/metric card. Minimum 320 x 240. Use r16 below 240 px short side. Do not nest more than one card level.

 | S02 / Diagonal frame A | TL72 TR16 BR72 BL16; width/height >=320 | Signature image/hero panel. Text inset >=48; avoid 96 x 96 corner exclusion zones at TL/BR. Do not use for plot area.

 | S03 / Diagonal frame B | TL16 TR72 BR16 BL72 | Mirrored companion. At most two photographic masks on one slide. Do not alternate arbitrarily between every card.

 | S04 / Pill | Radius height/2; height 56-64; inset x24 y12 | Short category label only, max 3 labels per slide. A printed pill is not an interactive button unless actual interaction exists.

 | S05 / Circle | 1:1 width/height; diameter 160-320 | Avatar or a single object; preserve head/subject. Never stretch a circle into an ellipse. Not a default chart container.

 | S06 / Quarter arc | Annulus sector 90 degrees; outer radius 160; inner radius 120 | One decorative arc max per slide. Scale uniformly; may rotate in 90-degree increments. No arbitrary squiggles. No metric meaning.

 | S07 / Inset band | Rectangle 64-96 px high; all corners r16 | One source/definition/takeaway region. Do not hide crucial context in a small band.

 | S08 / Divider tab | 48 x 8 or 8 x 48 rectangle; r4 | Small chapter accent. No resemblance to the reference loop logo.

 | S09 / Connector | 3 px teal, arrow head 16 x 12; 24 px endpoint clearance | Actual flow only; avoid crossing lines. Round joins permitted, but do not bend quantitative axes.

 | S10 / Photo plus metric | S02 photo + separate S01 metric, gap24 | Align bounding boxes; never overlap a number on the photograph by default. Preserve caption space.

 | S11 / Quote field | S01 panel, optional 44 px quotation glyph | Exact attributable quote; no invented testimonial. Glyph cannot cross reading area.

 | S12 / Charts | Rectangular plot area; containing panel may be r32 | Never clip bars, markers, intervals or axes to decorative curved frames. Quantitative marks do not inherit card corner radii.S01r32 / all cornersS0272 / 16 / 72 / 16S0316 / 72 / 16 / 72S051:1 circleS06 / quarter arcCategoryS04 / label only07 / COVE SYSTEM

Crop the image. Preserve the source.

“Image into shape” means non-destructive clipping. It does not mean converting a photograph into vector geometry.

 | ID | Required behavior

 | M01 / Source record | Retain original file. Record source/author, rights, original dimensions, focal point, generation status, caption and alt text. Never generate documentary proof.

 | M02 / Fit | Default cover for editorial photos; contain for diagrams, logos, evidence screenshots or any asset whose edges carry information. No stretching or baked-in frame that damages the source.

 | M03 / Mask choice | S02 for hero/large photo; S01 for secondary; S05 only avatar/object with sufficient clearance. Max two nonrectangular photo masks per slide.

 | M04 / Focal point | Normalized source coordinates fx, fy in [0,1]. Inspect the subject, then set point; .5,.5 is fallback, not a claim of correct composition. Keep relevant faces/hands outside curved corners.

 | M05 / Exact cover math | For source W, H and frame w, h: scale s=max(w/W, h/H); rendered rw=sW, rh=sH. Offset x=clamp(w/2-fx*rw, w-rw,0), y=clamp(h/2-fy*rh, h-rh,0). Clip after positioning; record offsets.

 | M06 / Example crop | 2400 x 1600 source into 720 x 900 frame, focal (.60,.45): s=.5625, rendered 1350 x 900, offset (-450,0). Visible source area 1280 x 1600; 46.67% of original width removed.

 | M07 / Resolution | For 13.333 x 7.5 inch master, a 720 x 900 frame occupies 5 x 6.25 in. The example delivers 256 effective PPI. Prefer >=150; minimum100 for photos. Evidence screenshots must also remain legible at final size.

 | M08 / Geometry | Cap large radius at min(72, shortSide/4), small at min(16, shortSide/8) for custom-sized diagonal masks. For standard >=320 frames use specified72/16. Apply uniform scaling, not arbitrary CSS percentage radius.

 | M09 / Text zones | Default separate solid text. For any intentional overlay, reserve 48 px inset and 96 px corner exclusions; verify contrast over full text region. Caption below image, gap16-24.

 | M10 / Export | HTML use SVG clipPath with explicit path. PPTX/Slides use native crop-to-shape if geometry supported. Otherwise retain original plus mask definition; disclose rasterized treatment, keep caption editable.

 | M11 / Fallback | If editor cannot reproduce diagonal corners, use S01 r32 and record substitution. Never approximate by distorting image or silently clipping evidence.

 | M12 / QA | Compare original and crop. Check focal point, lost context, headroom, transparency, caption, effectivePPI, mask bounds, cross-editor export and accessible description.

Image placement record:
assetId · sourceFile · sourceWidth/Height · rights · role
shapeId · frame[x, y, w, h] · radii[TL, TR, BR, BL]
fit · focal[fx, fy] · scale · offset[x, y] · effectivePPI
caption · alt · cropLimitations · exportFallback

For a CSS background image, object-position percentages do not directly equal the source focal coordinates above. Use calculated pixel offsets or an SVG image transform for exact placement.13 / COVE SYSTEM

Same source. Deliberate framing.

This code-native illustration demonstrates mask geometry and crop math. It is not documentary imagery.One source, two diagonal framesSynthetic vector source, not a photograph. Left exact crop keeps marked focal point centered. Right uses center crop for comparison.S02 / focal(.60,.45) / offset(-450,0)S03 / center(.50,.50) / offset(-315,0)SYNTHETIC MASK DEMONSTRATION / NOT A PHOTO

/* Standard diagonal frame at >=320 px short side */
 border-radius: 72px 16px 72px 16px; /* TL TR BR BL */
 /* For exact cross-tool reproduction use this 720x900 SVG path: */
 M72 0 H704 A16 16 0 0 1 720 16 V828 A72 72 0 0 1 648 900
 H16 A16 16 0 0 1 0 884 V72 A72 72 0 0 1 72 0 Z
 /* Source2400x1600; frame720x900; focal(.60,.45) */
 transform: translate(-450px,0px) scale(.5625);
 /* Clip AFTER transform; retain original source separately. */

For SVG, transform order above is translate then scale in the transformation matrix. For CSS use transform-origin:0 0 and verify offsets. The mask path is expressed in frame coordinates. PNG/JPEG sources use an SVG image element with the same rendered bounds.

Geometry examples are scaled. Preserve source files; inspect real images in the actual export tool.
