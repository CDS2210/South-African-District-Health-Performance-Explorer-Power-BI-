# Data Dictionary

## Fact_DHB
| Column          | Type    | Example        | Notes                                  |
|-----------------|---------|----------------|-----------------------------------------|
| DistrictID      | Text    | DC42           | Links to Dim_Geography                  |
| ProvinceID      | Text    | WC             | Redundant key for convenience           |
| Period          | Text    | 2023/24        | Financial year or YYYY-MM               |
| IndicatorID     | Text    | ANTENATAL20W   | Links to Dim_Indicator                  |
| Value           | Number  | 68.4           | Unit in Dim_Indicator                   |

## Fact_NMC
| Column      | Type   | Example    | Notes                             |
|-------------|--------|------------|------------------------------------|
| ProvinceID  | Text   | GP         |                                    |
| Month       | Date   | 2024-06-01 | First of month                     |
| ConditionID | Text   | MEASLES    | Links to Dim_Condition             |
| Cases       | Number | 132        | Raw case counts                    |

## Fact_Pop
| Column     | Type   | Example | Notes                                |
|------------|--------|---------|---------------------------------------|
| GeoID      | Text   | DC42    | ProvinceID or DistrictID              |
| Year       | Number | 2024    |                                       |
| AgeBand    | Text   | 0-4     | Optional for age-standardisation      |
| Sex        | Text   | All     | Optional                              |
| Population | Number | 512340  |                                       |

## Dim_Geography
| Column     | Type | Example     | Notes                              |
|------------|------|-------------|-------------------------------------|
| GeoID      | Text | DC42        | Primary key                         |
| District   | Text | Eden        |                                     |
| Province   | Text | Western Cape|                                     |
| Lat        | Num  | -33.9       | Centroid (optional)                 |
| Long       | Num  | 22.5        |                                     |

## Dim_Indicator
| Column          | Type | Example        | Notes                                   |
|-----------------|------|----------------|------------------------------------------|
| IndicatorID     | Text | ANTENATAL20W   | PK                                       |
| Name            | Text | Antenatal visit before 20 weeks |
| Unit            | Text | %              | %, rate per 100k, etc.                   |
| DesiredDirection| Text | Up             | “Up” means higher is better              |
| Definition      | Text | …              | Tooltip content                          |
| Source          | Text | DHB 2023/24    |                                          |

## Dim_Time
| Column | Type | Example | Notes                |
|--------|------|---------|----------------------|
| Date   | Date | 2024-06-01 | Calendar table   |
| Month  | Text | 2024-06  |                     |
| Year   | Num  | 2024    |                     |

## Dim_Condition
| Column      | Type | Example | Notes                 |
|-------------|------|---------|------------------------|
| ConditionID | Text | MEASLES | PK                     |
| Name        | Text | Measles |                        |
| Category    | Text | VaccinePreventable | Optional   |
