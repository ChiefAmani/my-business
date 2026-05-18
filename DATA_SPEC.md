# DATA_SPEC.md

## Project: My Business - Financial Model
## Format: JSON
## Purpose: To establish a foundational financial model for business model validation and KPI tracking.

## Top-Level Objects:

### 1. model_name (string)
- Description: Name of the financial model.

### 2. description (string)
- Description: A brief overview of the model's purpose and scope.

### 3. assumptions (object)
- Description: Key input variables driving the financial model.
- Structure: Each assumption is an object with:
    - `value` (number): The assumed numerical value.
    - `unit` (string): Unit of measurement (e.g., "$", "%", "customers").
    - `source` (string): Origin of the assumption (e.g., "Assumption", "Market Research", "Historical Data").

### 4. base_case_monthly_financials (object)
- Description: Calculated financial metrics for a typical month under base assumptions.
- Structure: Each financial metric is an object with:
    - `value` (number): The calculated numerical value.
    - `unit` (string): Unit of measurement (e.g., "$", "customers", "ratio").

### 5. key_performance_indicators (array of objects)
- Description: Critical metrics to track business performance and progress towards goals.
- Structure: Each KPI is an object with:
    - `name` (string): Full name of the KPI.
    - `unit` (string): Unit of measurement.
    - `current_value` (number): The latest calculated value.
    - `target` (string): The desired target value or range (e.g., "3:1 minimum", "TBD").
    - `formula` (string, optional): The formula used to calculate the KPI.

### 6. sensitivity_analysis (object)
- Description: Analysis of how changes in key assumptions impact core financial outcomes.
- Structure: Each sensitivity scenario is an object, typically showing the impact on key metrics (e.g., MRR, Net Profit) for different assumption values.

### 7. top_3_risks (array of objects)
- Description: Identification and assessment of the top risks to the business model.
- Structure: Each risk is an object with:
    - `risk` (string): Description of the risk.
    - `probability` (number, 1-5): Likelihood of the risk occurring.
    - `impact` (number, 1-5): Severity of the risk's effect.
    - `score` (number): Probability * Impact.
    - `mitigation` (string): Proposed actions to reduce or address the risk.

## Key Formulas (Examples):
- **Monthly Recurring Revenue (MRR):** `starting_customers * avg_revenue_per_customer_monthly`
- **Cost of Goods Sold (COGS):** `MRR * (1 - gross_margin_percentage)`
- **Gross Profit:** `MRR - COGS`
- **Net Profit:** `Gross Profit - monthly_operating_expenses`
- **LTV per Customer:** `avg_revenue_per_customer_monthly / monthly_churn_rate`
- **LTV:CAC Ratio:** `LTV per Customer / customer_acquisition_cost`

## Sample Data (Refer to financial_model_initial.json for current sample data)
