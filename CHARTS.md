# COVE — Chart guide 1.1.0

| ID | Rule |
| --- | --- |
| CH01 / Question | Comparison→bars/dots; trend→line; part-to-whole→100%stackedbar; distribution→histogram/dots; relationship→scatter; uncertainty→intervals; exact lookup→table. |
| CH02 / Bar | Horizontal preferred for long labels;<=8 categories on main slide.Sort by value unless ordinal/time order.Zero baseline required.Negative values around visiblezero.Square bar ends, even in rounded cards. |
| CH03 / Grouped comparison | 2-3 series per category,<=6categories; equal scales and consistent order.Use dotplot when groups become crowded.No dualaxes by default. |
| CH04 / Time series | Up to4series; true time spacing.Label nonzero domain if justified; missing actual points break line.Actual solid, target dashed, forecast dashed+boundary+label. |
| CH05 / Whole | Exclusive exhaustive categories, denominator explicit;<=5segments.Fixed order, totals reconcile; use a table if parts do not form a whole.Donut optional only2-5positive parts; bars preferred for precision. |
| CH06 / Distribution | Raw observations or documented bins.Label boundaries, count/sample size; include zero bins; compare with identical bins.No arbitrary smoothing/outlier deletion. |
| CH07 / Scatter | Paired observations with units, scope and n.Correlation is not cause.Fit only if justified with stated method; never fabricate a regression. |
| CH08 / Actual-target | Actual, target, period and benchmark definition.Bullet chart/dots preferred.Written threshold required for qualitative bands.Unknown status=Not assessed. |
| CH09 / Waterfall | Opening+signed additive changes=closing.Totals startzero; changes float from cumulative balance.Show connectors and signed labels; separate total/delta encoding. |
| CH10 / Heatmap | Sequential scale for magnitude; diverging only with meaningful midpoint.Values/legend required.Missing uses hatch+N/A, neverzero.Contrast label against each cell fill. |
| CH11 / Interval | Show supplied lower/upper/central value and range/confidence definition.No invented intervals; prediction and confidence intervals are different. |
| CH12 / Map | Only if geography matters.Rates for choropleth; rawcounts may need proportional symbols.Source coordinates/basemap licence, class bins, denominator, cutoff.Informational network differs from decoration. |
| CH13 / Canvas | Units at1920x1080.Read chart labels>=26px; Present >=30px.Legend/directlabels same minimum.Full plot should occupy>=55%of content width; split instead of shrink. |
| CH14 / Marks | Use5px line and14px marker atnative canvas;2px zeroaxis/outline,1px decorativegrid.4-6major ticks using1/2/2.5/5x10^n.Never use rounded bars,3D, area/volume pictograms or shadow as quantitative encoding. |
| CH15 / Color | Fixed series mapping:#123F43, #315F86, #A65332, #6F527C.Primaryfocus#FFB38Aon#F7F5EFrequires2px#123F43outline.No pale accent alone for meaningful marks.Status colors require state and threshold; do not assign palette decoration a status meaning. |
| CH16 / Typography | Direct labels preferred; avoid overlapping endpoints, slanted ticks and detached units.Resolve collision by widening, shortening truthful labels, or splitting.Critical caveats use body size, not footer. |
| CH17 / Numbers | Source, period, scope, units, denominator andcutoff explicit.40%→50%=+10percentage points or+25%relative; specifywhich.Compute raw, round display only. |
| CH18 / Missing | 0, null, N/A andNotassessed differ.No null-to-zero conversion; no silent interpolation.Show gaps, excluded sample and noncomparable periods. |
| CH19 / Semantics | Colors/labels consistent across deck.Pale focus outlined; series distinguished by marker/dash/directlabel, not hue alone.No default causal headline from association. |
| CH20 / Access and export | Provide concise accessible summary and underlying data table; SVGtitle/desc; editable native chart+source data if supported.SVGspecimen is not native chart master.Check actual render, textselection and readingorder where supported. |
| CH21 / Integrity gate | Recompute totals, deltas, percentages, denominators, rounding and intervals.Check domain/baseline, signs, nulls, seriesmapping, labelcollisions, source and final export. |
| CH22 / Trace record | chartID, question, type, datasetID, source locator, period/cutoff, units, denominator, fieldtypes, transformation, domain, ticks, mapping, focusreason, caveat, summary, QAresult. |

## Original detailed contracts

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

Q3 has no actual value; the actual line stays broken.Trend with missing periodQ1 actual28, Q2 42, Q3 missing, Q4 60. Target40. Domain0 to80. No interpolation.020406080Q1Q2Q3Q4Target402842Not available60Actual solid / target dashed / gap retainedD03 / D22 / No inferred trend across missing observations.ILLUSTRATIVE DATA

A defined whole.

A donut is optional; use bars when precision matters.Share of illustrative wholeA45%, B30%, C25%. Positive, exhaustive parts totaling100%.A / 45%B / 30%C / 25%100%Example wholeParts45 +30 +25 =100 / no source datasetD05 / Actual data sums to100%; exact values remain visible.ILLUSTRATIVE DATA

Contributions reconcile.

Opening and closing totals differ from signed changes.Illustrative waterfallOpening100, changes+25,-15,+10, closing120. Domain0 to160.04080120160100Open+25Add-15Loss+10Add120Close100 +25 −15 +10 =120 example unitsD09 / Signed changes, total bars and connectors; additive reconciliation checked.ILLUSTRATIVE DATA

Relationship, not causation.

Paired observations; no invented fit or causal claim.Scatter of five illustrative observationsPairs2,3;4,4;5,2;7,6;8,5. Both axes0 to10. No trend fit.00224466881010X / example units. Y / example units. n=5.D07 / Five observations; no generated regression line.ILLUSTRATIVE DATA

Magnitude and missingness.

Sequential bins; absent value has a distinct hatch.Illustrative heatmapR1 values20,40, missing.R2 60,80,100. Sequential score scale0 to100.2040N/A6080100ABCR1R20–20>20–40>40–60>60–80>80–100Example score / fixed0–100 / N/A is missingD10 / Values remain explicit. Hatch is reserved for missing data.

 | Underlying sample | Values

 | Bars / points | A40, B65, C80; scale0–100

 | Trend / points | Q1 28, Q2 42, Q3 null, Q4 60; target40; scale0–80

 | Shares / percent | A45, B30, C25; total100%

 | Waterfall / units | 100+25−15+10=120

 | Scatter / x, y | (2,3),(4,4),(5,2),(7,6),(8,5)

 | Heatmap / scores | R1[20,40, null]; R2[60,80,100]; scale0–100

The examples are SVG and their data are in example-data.json. They demonstrate appearance and encoding, not an interactive charting library. Apply slide token typography at production size.
