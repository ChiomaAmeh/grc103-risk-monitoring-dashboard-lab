# Risk register update - March

Chioma Ameh | Reg. No. C11/26/CGRCE/17567 | Northbridge Services (fictional)

Score = Likelihood x Impact. Bands: Low 1-4, Medium 5-9, High 10-16, Critical 17-25. An indicator colour is not automatically a risk score. Ratings, owners (roles) and dates are **proposed assumptions**; figures are observed from the fictional dataset.

| ID | Asset / process | Risk statement | March evidence (observed) | Existing control | L | I | Score | Owner | Actions | Review date |
|---|---|---|---|---|---|---|---|---|---|---|
| R-01 | Endpoint monitoring coverage | Unmonitored endpoints may allow malicious activity or unauthorised changes to go undetected, delaying detection and response. | Coverage 90.0% (108 of 120) - Red; gap 12 endpoints (Jan 2, Feb 5); eligible 100 to 120, monitored 95 to 108. | Monitoring agents; monthly coverage indicator (enrolment process assumed). | 4 | 3 | **12 High** | Endpoint Security Manager | A1, A2 | 27 Apr 2026 |
| R-02 | Critical-alert triage and review | Critical alerts not reviewed within 24 hours may delay discovery and containment of genuine incidents. | Timely review 70.0% (28 of 40) - Red; 12 alerts late (Jan 1, Feb 6); volume 20 to 40; unauthorised changes 1, 3, 5. | 24-hour review target; monthly indicator. | 4 | 4 | **16 High** | Security Operations Lead | A3, A4 | 20 Apr 2026 |
| R-03 | Backup and restoration | Failed restoration tests indicate backups may not be recoverable when needed, prolonging outage or causing data loss. | Restore success 80.0% (8 of 10) - Red; 2 failed in March, 1 in February; 3 in the last 20 tests. | Monthly restore testing (10 tests); success indicator. | 3 | 5 | **15 High** | Backup and Recovery Manager | A5, A6 | 20 Apr 2026 |
| R-04 | High-risk action tracking | Overdue high-risk actions leave known risks untreated, so exposure persists and may compound the other risks. | Overdue rate 40.0% (6 of 15) - Red; Jan 10.0%, Feb 25.0%; actions due rose 10 to 15. | Action tracking with due dates; monthly indicator. | 4 | 3 | **12 High** | Risk and Compliance Manager | A7, A8 | 27 Apr 2026 |

## Rating justifications

- **R-01 (L4, I3):** the gap exists now and is widening (2, 5, 12) and 5 unauthorised changes were confirmed, so undetected activity is likely. Impact 3: visibility is lost on 10% of the estate; the criticality of the 12 endpoints is unknown (assumption), so impact is not rated 4-5.
- **R-02 (L4, I4):** 30% of critical alerts were late and the rate has fallen three months running. Critical alerts are the main detection signal and delay extends attacker dwell time. Not 5: alerts are not proven incidents and no confirmed breach is evidenced.
- **R-03 (L3, I5):** a real restore failing is plausible given a 20% test failure rate, but a restore is only needed after an incident (frequency unknown). Failed recovery of critical data would mean severe, prolonged disruption. 15 is High, just below Critical (17+).
- **R-04 (L4, I3):** overdue actions are already at 40% and rising. Each overdue action extends exposure moderately; severity depends on which risks they treat, which the dataset does not state (assumption: some relate to R-01 to R-03).

## Escalation (exercise rules, not ICDFA policy)

All five indicators are Red in March, so each is escalated to its responsible manager within one working day (by **7 Apr 2026**): coverage - Endpoint Security Manager; alert review - Security Operations Lead; restore success - Backup and Recovery Manager; overdue actions - Risk and Compliance Manager; unauthorised changes - Information Security Manager. All four risk scores are High (10+), so all four also require management escalation. None is Critical: the dataset shows no confirmed loss.
