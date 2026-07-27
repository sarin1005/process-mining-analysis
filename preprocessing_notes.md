# Preprocessing Methodology and Assumptions

## Purpose

The original hospital billing event log contained timestamps and activity records but did not provide complete, interpretable resource information or direct activity-cost measures. To support resource, duration and cost analysis, the event log was enriched using documented assumptions.

## Preprocessing Steps

1. Imported the XES event log into R.
2. Converted the event log into a standard data frame.
3. Standardised column names.
4. Renamed the case identifier, activity and timestamp fields.
5. Assigned assumed processing durations to each activity.
6. Mapped activities to representative functional roles.
7. Assigned estimated hourly rates to each role.
8. Calculated estimated activity costs.
9. Preserved relevant case-level attributes.
10. Exported the enriched event log as a CSV file for use in Apromore.

## Key Assumptions

Activity durations were assigned because the source event log did not include usable processing durations for each activity. Role assignments were inferred from activity names because the original resource field contained missing or uninterpretable values.

Hourly rates were estimated using publicly available salary information. These values were used for educational analysis only and should not be interpreted as actual hospital staffing costs.

## Data Validation

When the enriched CSV was uploaded to Apromore, 69 rows were flagged because the generated start timestamp was later than the recorded end timestamp. These rows represented less than 1% of the dataset and were excluded from the imported event log after reviewing the validation report.

## Limitations

- Activity durations are assumed rather than directly observed.
- Functional roles are inferred from activity labels.
- Hourly rates are estimates based on external salary information.
- Cost results should therefore be interpreted as indicative rather than actual.
- Findings are intended for academic demonstration and process-analysis practice.

Apromore flagged 69 timestamp-validation errors during import. The affected records were reviewed and excluded because they represented less than 1% of the dataset.