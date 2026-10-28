# Vienna Next Bus v9 — timetable marker audit

Source reviewed: `Busfahrplan Midesason 2026 A Plan`, validity 12.10–01.11.2026.

## Results

- Compared marker entries with the supplied timetable image, including row and duty-column positions.
- Preserved the existing departure timetable: 36 stops, 48 line/stop schedule records, 893 time entries and matching code entries; the schedule arrays are byte-for-byte semantically identical to version 5.
- 45 operational events are recorded across the four lines.
- All arrival times derived for cells containing `ENDE` are marked as inferred; the source does not print those clock times.

## Corrections from v8

| Item | Verified assignment |
|---|---|
| Yellow pause | Printed value is **11:05 P, S1**, not 10:55. |
| Green pause 1 | **13:45 P, G1** — third green duty column. |
| Green pause 2 | **14:45 P, S6** — fourth green duty column. This is S6 after the yellow-to-green change at 13:20; its green arrival at 13:45 is not a pause. |
| Green duty end | Added **17:00 ENDE, G1** as an inferred Station 47 arrival from 16:37 at stop 39 plus the repeated 23-minute segment. |
| Blue duty ends | Added inferred Station 1 arrival times for all 11 printed blue `ENDE` cells, using the matching column’s Kursalon time plus the repeated 6-minute segment. |
| Yellow duty ends | Added inferred Station 1 arrival times for all six yellow `ENDE` cells, using the matching column’s Schwarzenbergplatz time plus the repeated 7-minute segment. |
| Red D5 duty end | **17:30 ENDE at KHM**, inferred from 17:22 at Naschmarkt plus the 8-minute segment. |
| Red P/Y | Linked S6 at KHM 11:30 to the matching yellow S6 service at Staatsoper 12:00. |
| Blue B/R | Retained B/R at MAK 11:48 and included the same D5 duty’s terminal B/R annotation at Staatsoper 11:58. |
| Blue E | Removed the unsupported off-duty interpretation. The source says `E`, not `ENDE`, and later times continue in that column; retained separately as an unclassified annotation. |

## All recorded events

| Line | Stop | Time | Marker | Bus | Time basis |
|---|---|---:|---|---|---|
| Blue | 13 — MAK/Wien-Mitte (Ankunft) | 10:00 | P | D1 | Printed marker/time |
| Blue | 13 — MAK/Wien-Mitte (Ankunft) | 11:00 | P | D2 | Printed marker/time |
| Blue | 13 — MAK/Wien-Mitte (Ankunft) | 11:48 | B/R | D5 | Printed marker/time |
| Blue | 1 — Staatsoper (Ankunft) | 11:58 | B/R | D5 | Printed marker/time |
| Blue | 13 — MAK/Wien-Mitte (Ankunft) | 12:04 | P | ABL1 | Printed marker/time |
| Blue | 13 — MAK/Wien-Mitte (Ankunft) | 12:28 | P | D3 | Printed marker/time |
| Blue | 13 — MAK/Wien-Mitte (Ankunft) | 13:24 | P | D4 | Printed marker/time |
| Blue | 13 — MAK/Wien-Mitte (Ankunft) | 14:36 | P | ABL1 | Printed marker/time |
| Blue | 13 — MAK/Wien-Mitte (Ankunft) | 15:00 | P | D1 | Printed marker/time |
| Blue | 1 — Staatsoper (Ankunft) | 15:58 | ENDE | ABL | Estimated terminal arrival |
| Blue | 13 — MAK/Wien-Mitte (Ankunft) | 16:12 | P | D2 | Printed marker/time |
| Blue | 1 — Staatsoper (Ankunft) | 17:34 | ENDE | D3 | Estimated terminal arrival |
| Blue | 1 — Staatsoper (Ankunft) | 17:34 | ENDE | D3 | Estimated terminal arrival |
| Blue | 1 — Staatsoper (Ankunft) | 17:58 | ENDE | D6 | Estimated terminal arrival |
| Blue | 1 — Staatsoper (Ankunft) | 17:58 | ENDE | D6 | Estimated terminal arrival |
| Blue | 1 — Staatsoper (Ankunft) | 18:22 | ENDE | D1 | Estimated terminal arrival |
| Blue | 1 — Staatsoper (Ankunft) | 18:22 | ENDE | D1 | Estimated terminal arrival |
| Blue | 1 — Staatsoper (Ankunft) | 18:46 | ENDE | D4 | Estimated terminal arrival |
| Blue | 1 — Staatsoper (Ankunft) | 18:46 | ENDE | D4 | Estimated terminal arrival |
| Blue | 1 — Staatsoper (Ankunft) | 19:10 | ENDE | D2 | Estimated terminal arrival |
| Blue | 1 — Staatsoper (Ankunft) | 19:10 | ENDE | D2 | Estimated terminal arrival |
| Red | 2 — KHM (Ankunft) | 10:30 | P/B | ABL | Printed marker/time |
| Red | 2 — KHM (Ankunft) | 11:30 | P/Y | S6 | Printed marker/time |
| Red | 2 — KHM (Ankunft) | 12:00 | P | R1 | Printed marker/time |
| Red | 2 — KHM (Ankunft) | 13:00 | P | D5 | Printed marker/time |
| Red | 2 — KHM (Ankunft) | 14:30 | P/B | D6 | Printed marker/time |
| Red | 2 — KHM (Ankunft) | 15:00 | P | R1 | Printed marker/time |
| Red | 2 — KHM (Ankunft) | 17:30 | ENDE | D5 | Estimated terminal arrival |
| Yellow | 1 — Staatsoper (Ankunft) | 11:05 | P | S1 | Printed marker/time |
| Yellow | 1 — Staatsoper (Ankunft) | 11:50 | P | S3 | Printed marker/time |
| Yellow | 1 — Staatsoper (Ankunft) | 12:10 | P | S2 | Printed marker/time |
| Yellow | 1 — Staatsoper (Ankunft) | 12:57 | P | S4 | Printed marker/time |
| Yellow | 1 — Staatsoper (Ankunft) | 13:20 | Y/G | S6 | Printed marker/time |
| Yellow | 1 — Staatsoper (Ankunft) | 14:05 | P | S5 | Printed marker/time |
| Yellow | 1 — Staatsoper (Ankunft) | 15:12 | P | S1 | Printed marker/time |
| Yellow | 1 — Staatsoper (Ankunft) | 15:57 | P | S3 | Printed marker/time |
| Yellow | 1 — Staatsoper (Ankunft) | 16:20 | ENDE | S2 | Estimated terminal arrival |
| Yellow | 1 — Staatsoper (Ankunft) | 17:05 | ENDE | S4 | Estimated terminal arrival |
| Yellow | 1 — Staatsoper (Ankunft) | 17:20 | ENDE | S6 | Estimated terminal arrival |
| Yellow | 1 — Staatsoper (Ankunft) | 17:35 | ENDE | S1 | Estimated terminal arrival |
| Yellow | 1 — Staatsoper (Ankunft) | 18:05 | ENDE | S5 | Estimated terminal arrival |
| Yellow | 1 — Staatsoper (Ankunft) | 18:35 | ENDE | S3 | Estimated terminal arrival |
| Green | 47 — Votivkirche (Ankunft) | 13:45 | P | G1 | Printed marker/time |
| Green | 47 — Votivkirche (Ankunft) | 14:45 | P | S6 | Printed marker/time |
| Green | 47 — Votivkirche (Ankunft) | 17:00 | ENDE | G1 | Estimated terminal arrival |

## Limitations

- The blue `E` annotation has no legend. It is not treated as an off-duty marker to avoid a false warning.
- The source cells for `ENDE` do not contain numeric times. The app marks the computed terminal arrival estimates as inferred, rather than printing them as source values.
- JSON validation passed, the departure arrays match v5 exactly, and JavaScript syntax passed `node --check`. A live GitHub Pages deployment/browser-toast test has not been run.
