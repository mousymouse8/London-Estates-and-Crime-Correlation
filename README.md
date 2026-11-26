# London-Estates-and-Crime-Correlation

# London Real Estate and Crime Analysis

A Power BI analytics project that prepares residential property and police-recorded crime data for borough-level comparison across London. The study focuses on **2020–2023** and asks whether changes in reported crime coincide with changes in residential property values.

## Dataset availability

**The raw datasets were too large to upload to this repository. You can download both datasets from the original Kaggle links in the [References](#references) section below.**

## Analysis objectives

- Compare annual residential property values and year-over-year changes across London boroughs, where historical price observations are available.
- Measure year-over-year changes in reported crime incidents and identify boroughs with the largest and smallest changes.
- Compare property and crime trends at the same geographic and time levels to explore whether they move together.

## Data and methodology

| Step | Work documented |
| --- | --- |
| **Property data preparation** | Reviewed available fields, removed unused columns, and standardized numeric types. The report records no duplicate property rows in the source extract reviewed. |
| **Crime data preparation** | Removed repeated crime IDs and filtered the UK-wide source to Metropolitan Police records for the London analysis. |
| **Geographic enrichment** | Built separate lookup tables to associate property postcodes and crime LSOA codes with London borough names. Each lookup includes geographic coordinates. |
| **Power BI modeling** | Connected the postcode lookup to property records and the LSOA lookup to crime records. These keys support consistent borough labels for grouped analysis. |
| **Data documentation** | Documented source and cleaned fields, data types, and lookup keys in the report’s data dictionaries. |

**LSOA** stands for Lower Layer Super Output Area, a small statistical geography used in the crime records.

### Power BI relationships

| Lookup key | Records it connects to | Relationship |
| --- | --- | --- |
| Postcode lookup → `postcode` | Property records → `postcode` | One-to-many |
| LSOA lookup → `LSOA code` | Crime records → `LSOA code` | One-to-many |

## Interpreting the analysis

- The project report documents the research question, data preparation, and model. It gives a **30% increase in reported crime** and a **15% decrease in property prices** as background figures. These figures are unverified in the report, which provides no supporting calculations or borough-level results.
- The documented property fields include **estimated current prices**. Verifying annual price changes for 2020–2023 requires checking for dated historical price observations in the source data.
- Compare **reported incident counts** across boroughs and years. A population-based crime rate requires a population denominator, and crime density per square kilometre requires land-area data.
- Any relationship identified through this comparison should be interpreted as an **association**. Property type, size, location, and market demand can also influence values.

## References

- [Crimes in UK — Kaggle](https://www.kaggle.com/datasets/ndaruga/crimes-in-uk) provides monthly police-recorded crime data, categories, outcomes, and geographic identifiers.
- [House Price Data — Kaggle](https://www.kaggle.com/datasets/jakewright/house-price-data?resource=download) provides property characteristics, locations, and estimated values.
