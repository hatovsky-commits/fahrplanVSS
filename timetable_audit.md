# Vienna Next Bus v21 — compact event status audit

## Adjustments
- P/B is interpreted as pause, then blue. Duration is calculated as the next matching blue-line departure at the same stop minus the pause time.
- Red KHM R1 at 18:00 with marker NT is recorded as a night tour, not off duty.
- Compact labels: `☕ 92m` for pause duration, `⛔ Off duty`, `🔀 BLUE → YELLOW` for colour change, `🌙 NT` for night tour, and `🚌 IN 4m` for the next passenger service.
- Labels are placed only on exact event/departure cards. The next passenger service label is attached only to the immediately following scheduled departure at that stop.
- The six previously restored blue-line cells are preserved, with all 899 time/code entries. Day filtering remains disabled as requested.
- The preview-clock code from working version 20 is retained unchanged.

## Calculated P/B examples
- ABL at 10:30 → same-stop blue 12:02 = 92 min (ABL).
- D6 at 14:30 → same-stop blue 16:02 = 92 min (D6).

## Night-tour marker
- Red line, KHM (Ankunft), 18:00, R1, NT → `🌙 NT`; it is not interpreted as `ENDE`.

## Validation
- JSON parses and contains 36 stops, 46 plan events, and 899 time entries.
- Time/code array lengths match in all stop/line entries.
- Inline JavaScript passes `node --check`.
- ZIP contains `index.html` and `timetable.json`.

Note: this is a local code/data validation, not a live GitHub Pages deployment test.
