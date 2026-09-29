# Excel-ready backlink tracker instructions

Open `backlink_tracker_excel_ready.csv` in Excel or Google Sheets and save it as `.xlsx`.

## Formula columns
- **Days Open** calculates the number of days since outreach, or since Date Added when outreach has not started.
- **Next Action** is a manual action field.
- Update **Status** using: Not Started, Researched, Pitched, Follow-up 1, Follow-up 2, Accepted, Rejected, Published, Not Relevant.
- Update **Link Status** using: Not Live, Live, Removed, Needs Review.

## Recommended summary formulas
Place these in a Summary sheet after importing the CSV:

- Total prospects: `=COUNTA('backlink_tracker_excel_ready'!G2:G1000)`
- Pitches sent: `=COUNTIF('backlink_tracker_excel_ready'!O2:O1000,"Pitched")+COUNTIF('backlink_tracker_excel_ready'!O2:O1000,"Follow-up 1")+COUNTIF('backlink_tracker_excel_ready'!O2:O1000,"Follow-up 2")`
- Live backlinks: `=COUNTIF('backlink_tracker_excel_ready'!S2:S1000,"Live")`
- Published placements: `=COUNTIF('backlink_tracker_excel_ready'!O2:O1000,"Published")`
- Response/acceptance rate: `=IFERROR((COUNTIF('backlink_tracker_excel_ready'!O2:O1000,"Accepted")+COUNTIF('backlink_tracker_excel_ready'!O2:O1000,"Published"))/COUNTIF('backlink_tracker_excel_ready'!O2:O1000,"<>Not Started"),0)`

Replace `REPLACE_WITH_LIVE_URL` with the actual target URL before outreach. Do not use paid, irrelevant, automated, or spammy link sources.
