# Climate Method

## Approach
1) **Spend-based emissions** (GHG Protocol Scope 3) when we only know $ spent:
   - `kgCO₂e = USD × EF(kgCO₂e/USD) for category`
2) **Electricity override** for Utilities when we have kWh and US region:
   - `kgCO₂e = kWh × EF(kgCO₂e/kWh)` (EPA eGRID). If kWh unknown, fallback to spend-based.

## Category Mapping
- Map Plaid Personal Finance primary categories to emissions factors.
- Store factors in a versioned file (YAML/JSON) with clear source + year.

## Sources (examples)
- GHG Protocol (spend-based method): https://ghgprotocol.org/
- UK Government GHG Conversion Factors (annual tables): https://www.gov.uk/government/collections/government-conversion-factors-for-company-reporting
- EPA eGRID subregion emission rates: https://www.epa.gov/egrid

## Limitations to disclose
- Spend-based factors are averages; merchant mix and regional differences can vary.
- Electricity intensity varies by grid and year; use latest available dataset and note the year.
- Results are **estimates**, intended for awareness and actionable direction, not formal reporting.

## Deliverables for the Climate module
- Factor file (YAML/JSON) with source and year.
- Mapping file: Plaid PFC → factor key.
- Computation service that returns:
  - monthly total kgCO₂e,
  - by-category breakdown,
  - 2 concrete reduction suggestions tied to the user’s top driver(s).
