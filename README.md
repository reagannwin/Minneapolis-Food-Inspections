# Minneapolis Food Inspections

An analysis of food inspection data from the City of Minneapolis, aimed at identifying the key factors that affect whether a food service business passes or fails a health inspection. The goal is to give restaurant owners, entrepreneurs, and operators actionable insight into what tends to drive inspection outcomes — so they can better prepare before opening or during ongoing operations.

---

## Project Goal

Minneapolis requires regular health inspections for all food service establishments. Violations can result in failed inspections, fines, or closures. This project examines historical inspection records to surface patterns such as:

- Which violation types are most common and most likely to cause a failed inspection
- How risk level, facility category, and neighborhood correlate with inspection scores
- What factors most strongly predict a poor inspection outcome
- Geographic trends — which areas or facility types tend to underperform

The end product is intended to serve as a practical reference for anyone navigating the Minneapolis food licensing and inspection process.

---

## Dataset

**Source:** City of Minneapolis food inspection records  
**Size:** 41,646 inspection records across 2,678 unique facilities  
**Time range:** 2023–2024

### Key Fields

| Field | Description |
|-------|-------------|
| `BusinessName` | Name of the food establishment |
| `FacilityCategory` | Type of establishment (Restaurant, Grocery, Food Truck, etc.) |
| `RiskLevel` | City-assigned risk tier (1 = highest risk, 3 = lowest) |
| `InspectionType` | Routine, Follow-up, Complaint, etc. |
| `InspectionResult` | Pass, Fail, or Conditional |
| `InspectionScore` | Numeric score (44–100) |
| `ViolationPriority` | Priority 1 (critical) through Priority 3 (minor) |
| `ViolationPoints` | Points deducted per violation (0–4) |
| `FoodCodeItem` | Specific food code section violated |
| `Neighborhood` / `Ward` | Location context |
| `Latitude` / `Longitude` | Coordinates for spatial analysis |

**Facility breakdown:**
- Restaurants: ~75.6% of records
- Institutions, groceries, meat markets, food trucks, caterers, and others make up the rest

---

## Current Progress

### Completed
- **Data cleaning** — selected 25 relevant columns, removed incomplete records, resulting in 41,646 clean rows
- **Unique facility identification** — combined parcel ID (APN) and business name into a normalized `unique_id` to track individual locations across multiple inspections
- **Missing value analysis** — documented gaps in violation priority (~15.5%), APN (~0.7%), and neighborhood (~1.5%) fields
- **Cleaned dataset saved** — `cleaned_food_inspections.csv`

### In Progress
- Exploratory visualizations (score distributions, inspection timelines, category comparisons)

### Planned
- Violation pattern analysis — most frequent and most impactful violations by facility type
- Geographic analysis — neighborhood- and ward-level inspection performance maps
- Risk factor analysis — which combinations of factors correlate with low scores
- Predictive modeling — estimating inspection outcome likelihood based on facility attributes

---

## Repository Structure
