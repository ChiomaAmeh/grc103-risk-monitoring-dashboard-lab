# Calculations, thresholds and results

Chioma Ameh | Reg. No. C11/26/CGRCE/17567 | GRC103 Module 4 Lab 2 | **All data fictional.**

The editable workbook with live formulas is `../workbook/GRC103_Lab4_Risk_Monitoring_Dashboard_Chioma_Ameh_C11-26-CGRCE-17567.xlsx`. This page shows the same formulas and results so they can be read directly on GitHub.

## 1. Source data (as given in the brief)

| Measure | Jan | Feb | Mar |
|---|---|---|---|
| Eligible endpoints | 100 | 100 | 120 |
| Actively monitored endpoints | 98 | 95 | 108 |
| Critical alerts generated | 20 | 30 | 40 |
| Critical alerts reviewed within 24 hours | 19 | 24 | 28 |
| Confirmed unauthorised file changes | 1 | 3 | 5 |
| Restore tests performed | 10 | 10 | 10 |
| Successful restore tests | 10 | 9 | 8 |
| High-risk actions due in month | 10 | 12 | 15 |
| High-risk actions overdue at month end | 1 | 3 | 6 |

## 2. Indicator formulas (workbook sheet `Indicators`)

Percentages use the brief's `x 100` form and are displayed to one decimal place. A zero denominator returns `N/A` (never 0% or 100%); no denominator is zero in this dataset.

| Indicator | Formula (example: January) |
|---|---|
| Monitoring coverage (%) | `=IF(Data!B5=0,"N/A",Data!B6/Data!B5*100)` = Active / Eligible x 100 |
| Timely critical-alert review (%) | `=IF(Data!B7=0,"N/A",Data!B8/Data!B7*100)` = Reviewed within 24h / Critical alerts x 100 |
| Restore-test success (%) | `=IF(Data!B10=0,"N/A",Data!B11/Data!B10*100)` = Successful / Performed x 100 |
| Overdue high-risk action rate (%) | `=IF(Data!B12=0,"N/A",Data!B13/Data!B12*100)` = Overdue / Due x 100 |
| Confirmed unauthorised changes (count) | `=Data!B9` (used directly as a count) |

## 3. Thresholds (classroom thresholds from the brief)

| Indicator | Green | Amber | Red |
|---|---|---|---|
| Monitoring coverage | >= 98% | >= 95% and < 98% | < 95% |
| Timely review | >= 95% | >= 85% and < 95% | < 85% |
| Restore success | 100% | >= 90% and < 100% | < 90% |
| Overdue actions | <= 10% | > 10% and <= 20% | > 20% |
| Unauthorised changes | 0 | 1-2 | >= 3 |

Status formula pattern (coverage, higher is better): `=IF(ISNUMBER(C5),IF(C5>=Thresholds!$B$5,"Green",IF(C5>=Thresholds!$C$5,"Amber","Red")),"N/A")`. Classification uses **unrounded** values.

## 4. Results and classification

| Indicator | Jan value | Feb value | Mar value | Jan status | Feb status | Mar status |
|---|---|---|---|---|---|---|
| Monitoring coverage | 98.0% | 95.0% | 90.0% | Green | Amber | Red |
| Timely critical-alert review | 95.0% | 80.0% | 70.0% | Green | Red | Red |
| Restore-test success | 100.0% | 90.0% | 80.0% | Green | Amber | Red |
| Overdue high-risk action rate | 10.0% | 25.0% | 40.0% | Green | Red | Red |
| Confirmed unauthorised changes (count) | 1 | 3 | 5 | Amber | Red | Red |

Values exactly on a threshold are classified by the rule: Jan coverage 98.0 = Green; Jan timely review 95.0 = Green; Feb coverage 95.0 = Amber; Feb restore success 90.0 = Amber; Jan overdue rate 10.0 = Green.

**March: all five indicators are Red** (January: four Green, one Amber).

## 5. Supporting calculations

| Measure | Calculation | Jan | Feb | Mar |
|---|---|---|---|---|
| Coverage gap (endpoints) | Eligible - Active | 2 | 5 | 12 |
| Active endpoints needed for Green (>= 98%) | ROUNDUP(Eligible x 98%) | 98 | 98 | 118 |
| Additional endpoints needed to reach Green | Needed - Active | 0 | 3 | 10 |
| Critical alerts not reviewed within 24h | Generated - Reviewed | 1 | 6 | 12 |
| Share of critical alerts reviewed late | (Generated - Reviewed) / Generated x 100 | 5.0% | 20.0% | 30.0% |
| Alert volume index (Jan = 100) | Generated / Jan generated x 100 | 100 | 150 | 200 |
| Failed restore tests | Performed - Successful | 0 | 1 | 2 |
| Overdue high-risk actions (count) | From data | 1 | 3 | 6 |

Change in eligible endpoints Feb to Mar: **+20**; change in actively monitored endpoints: **+13**; so the coverage gap rose by **+7** (5 to 12). A rising monitored count does not mean better coverage - the denominator grew faster.

## 6. Observed vs assumed

- **Observed / calculated:** every figure, status and the coverage gap above (from the fictional dataset).
- **Assumed:** possible causes, likelihood and impact ratings, owners (roles), the report date (6 Apr 2026) and deadlines.
- Three monthly observations cannot establish a reliable long-term trend or forecast; an alert is not necessarily an incident; correlation does not prove causation.