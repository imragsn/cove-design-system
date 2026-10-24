# COVE — Chart execution contracts

10 / COVE SYSTEM

Choose the question before the chart.

Charts are evidence instruments. Every type needs a reason, a data contract and an interpretation boundary.

 | ID / question | Preferred chart | Data / restriction

 | D01 / Compare categories | Horizontal bars | Category + numeric value + unit. <=8 categories main slide; sort by value unless chronological/ordinal. Zero baseline; negative values around visible zero.

 | D02 / Compare groups | Grouped bars or dot plot | Two or three series per category; <=6 categories. Shared scale and consistent order. Do not compare unaligned floating cards.

 | D03 / Trend | Line | Ordered time + numeric measure. Up to4 series; real time spacing. Unequal intervals are not equally spaced. Label nonzero baseline and explain rationale.

 | D04 / Part-to-whole | 100% stacked bar | Exhaustive, mutually exclusive categories with denominator. Show count/sample size. Use consistent segment order, <=5 categories. Do not stack unrelated measures.

 | D05 / Simple share | Donut, optional | Only positive parts of a known whole; 2-5 segments; sum reconciles to100%. Prefer bar for precise comparisons. Ring thickness30% outer radius; no exploding segments.

 | D06 / Distribution | Histogram or dot plot | Raw observations or documented bins. Label bin boundaries and counts; compare same bins, include zero count bins. Never smooth away outliers.

 | D07 / Relationship | Scatter | Paired x/y records with units; same record per point. Correlation does not prove cause. Never invent a trend fit; disclose sample/fit method.

 | D08 / Actual vs target | Bullet / paired dots | Actual, target, period and explicit benchmark definition. Target marker labeled; qualitative bands only with approved thresholds.

 | D09 / Change contribution | Waterfall | Opening balance, signed additive changes, closing balance. Opening + changes = closing; show connector, signed labels and total vs delta encoding.

 | D10 / Many comparisons | Heatmap | Row/column numeric matrix with known scale. Sequential darkening for magnitude; diverging scale only with meaningful midpoint. Values/legend required; missing has distinct pattern.

 | D11 / Uncertainty | Range / interval plot | Center + lower/upper bound, confidence level or range definition if supplied. Distinguish prediction from confidence interval. Never manufacture uncertainty.

 | D12 / Flow | Process diagram, or Sankey if true quantities | A simple arrow is not a quantitative flow. Sankey requires conserved quantities and compatible units; audit nodes before use.

 | D13 / Exact lookup | Table | When precise values, long labels or mixed measures matter more than pattern. Right-align numbers, include units and source.

 | D14 / Geography | Map only if geography matters | Use rates for choropleth; raw counts may require proportional symbols. Publish denominator/class bins; do not infer impact from land area.11 / COVE SYSTEM

Chart anatomy, without ambiguity.

All chart units below refer to a 1920 x 1080 slide. Smaller previews are scaled illustrations.

 | Contract | Specification

 | D15 / Frame | Minimum plot760 x360; recommended evidence region1100 x560. Title and takeaway outside plot. Reserve left144/right48/top72/bottom96 initially; increase for labels rather than reduce type.

 | D16 / Text | Read label26 px, Present30 px; chart heading44 px; explanatory copy30/36. Units in axis title or title; no unexplained K/M abbreviations.

 | D17 / Axes | 4-6 major ticks, human-readable intervals1/2/2.5/5 x10^n. Grid1 px line token, zero axis2 px teal; meaningful series>=3:1. Numeric baseline and any breaks explicit.

 | D18 / Marks | Line5 px; markers14 px; bar max width112 px; inner gap40% of bar width as starting point. Bars square-ended. Focus pale fill outlined2 px teal. No shadows/gradient/3D on values.

 | D19 / Category encoding | Use fixed semantic series mapping across deck; same category always same color/marker. Dark series palette supports five; line max4. Apricot is a highlight, not a new category by default.

 | D20 / Direct labels | Label at line ends with >=16 px separation and24 px plot clearance. Resolve collisions by expanding or splitting; do not overlap or hide values. Legend if needed in reading order, not color order.

 | D21 / Formatting | Consistent precision/unit; right-align decimals in tables. Locale follows user. Distinguish percentage change from percentage points. Negative sign not only red; estimated value explicitly labeled.

 | D22 / Missing | Missing is null;0 is real zero. Break lines at null, no silent interpolation. For heatmap use hatch/Not available; for bar show Not available outside axis rather than zero-width bar.

 | D23 / States | Actual solid; target dashed + label; forecast dashed + label and boundary date. Confidence band only from provided bounds. Patterns supplement color; no invented status thresholds.

 | D24 / Focus | One primary highlight per chart, at most2 callouts. Label reason for highlighting. Keep decoration outside plot; do not crop axes/intervals to rounded or diagonal mask.

 | D25 / Integrity | Shared scales for comparable panels. No dual axes by default; separate aligned plots. No truncated bar axis, area/volume distortion, stock icons scaled as values or arbitrary pie perspective.

 | D26 / Alternatives | Provide underlying data table and a concise accessible summary. HTML SVG requires title/desc; PDF reading order and selectable labels checked where supported.

 | D27 / Source | Source locator, period/cutoff, denominator, transformation and caveat adjacent. Labels actual/target/forecast/illustrative must survive export.

 | D28 / QA | Recompute totals/deltas/percentages. Test sign, rounding, sample size, null vs0, axis/domain, intervals, label collisions, category mapping, focus and source. Inspect actual export.

Chart record:
chartId · question · chartType · datasetId · sourceLocator
period/cutoff · units · denominator · fields/types · missingPolicy
transformation · domain/baseline · ticks · seriesMapping
labels · focusReason · caveat · accessibleSummary · exportQA12 / COVE SYSTEM

Six ways to show the evidence.

Rendered from example-data.json. No real organization, outcome or source dataset is implied.ILLUSTRATIVE DATA

Comparison, on one scale.

Bar lengths encode value; C is the focal category.Horizontal barsA40, B65, C80 example points. Zero baseline, axis0 to100.020406080100A40B65C80Example points / 0–100D01 / Square-ended bars; common baseline; apricot outlined in teal.ILLUSTRATIVE DATA

A gap is not zero.

Q3 has no actual value; the actual line stays broken.Trend with missing periodQ1 actual28,Q2 42,Q3 missing,Q4 60. Target40. Domain0 to80. No interpolation.020406080Q1Q2Q3Q4Target402842Not available60Actual solid / target dashed / gap retainedD03 / D22 / No inferred trend across missing observations.ILLUSTRATIVE DATA

A defined whole.

A donut is optional; use bars when precision matters.Share of illustrative wholeA45%,B30%,C25%. Positive, exhaustive parts totaling100%.A / 45%B / 30%C / 25%100%Example wholeParts45 +30 +25 =100 / no source datasetD05 / Actual data sums to100%; exact values remain visible.ILLUSTRATIVE DATA

Contributions reconcile.

Opening and closing totals differ from signed changes.Illustrative waterfallOpening100,changes+25,-15,+10,closing120. Domain0 to160.04080120160100Open+25Add-15Loss+10Add120Close100 +25 −15 +10 =120 example unitsD09 / Signed changes, total bars and connectors; additive reconciliation checked.ILLUSTRATIVE DATA

Relationship, not causation.

Paired observations; no invented fit or causal claim.Scatter of five illustrative observationsPairs2,3;4,4;5,2;7,6;8,5. Both axes0 to10. No trend fit.00224466881010X / example units. Y / example units. n=5.D07 / Five observations; no generated regression line.ILLUSTRATIVE DATA

Magnitude and missingness.

Sequential bins; absent value has a distinct hatch.Illustrative heatmapR1 values20,40,missing.R2 60,80,100. Sequential score scale0 to100.2040N/A6080100ABCR1R20–20>20–40>40–60>60–80>80–100Example score / fixed0–100 / N/A is missingD10 / Values remain explicit. Hatch is reserved for missing data.

 | Underlying sample | Values

 | Bars / points | A40,B65,C80; scale0–100

 | Trend / points | Q1 28,Q2 42,Q3 null,Q4 60; target40; scale0–80

 | Shares / percent | A45,B30,C25; total100%

 | Waterfall / units | 100+25−15+10=120

 | Scatter / x,y | (2,3),(4,4),(5,2),(7,6),(8,5)

 | Heatmap / scores | R1[20,40,null];R2[60,80,100]; scale0–100

The examples are SVG and their data are in example-data.json. They demonstrate appearance and encoding, not an interactive charting library. Apply slide token typography at production size.
