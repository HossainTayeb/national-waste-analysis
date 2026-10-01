# Data Dictionary

## Wastes.csv

| Column | Type | Description |
|---|---|---|
| Case_ID | numeric | Identifier for each waste process case (not guaranteed unique - see analysis notes) |
| Year_State_ID | numeric | Foreign key to Year_State_ID.csv |
| Category | character | Broad waste material classification |
| Type | character | Detailed waste material classification |
| Stream | character | Waste source: MSW (municipal), C&I (commercial/industrial), C&D (construction/demolition) |
| Fate | character | Waste destination: Disposal, Recycling, Energy recovery, Long-term storage, Waste reuse |
| Tonnes | numeric | Quantity of waste, in tonnes |
| Core_Non-core | character | Core waste vs. non-core (mining/agriculture-origin) waste |
| Description | character | Free-text summary including embedded environmental impact score (1-10) and feedback |

## Year_State_ID.csv

| Column | Type | Description |
|---|---|---|
| ID | numeric | Primary key, joins to Wastes.csv via Year_State_ID |
| Year | character | Australian financial year (e.g. "2020-2021") |
| State | character | Australian state/territory, or "Australia" (national aggregate) |
| Economic_Growth | numeric | Year-on-year percentage economic growth for that state |
