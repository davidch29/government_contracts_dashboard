# U.S. Army Contract Spending Analysis

## Overview

An interactive Power BI dashboard analyzing $103 billion in U.S. Army contract spending across 122,000+ transactions in FY2025. This project demonstrates the ability to work with federal government data and extract insights relevant to defense contractors and government IT firms.

## Business Problem

Defense contractors and government IT firms need visibility into federal spending patterns—which agencies award the most contracts, who wins them, where work is performed, and how much goes to small businesses. This intelligence helps companies identify opportunities and understand the competitive landscape.

## Data Source

**USASpending.gov** - Official source for federal spending data
- U.S. Department of the Army contracts
- Fiscal Year 2025
- 122,000+ contract transactions
- 17,000+ unique contractors

## Key Features

### Page 1: Contract Overview
- KPI cards (Total Obligations, Contract Count, Unique Contractors, Small Business %)
- Top 10 Contractors by Obligations
- Top 10 States by Contract Performance Location
- Cumulative Spending Over Time
- Business Size Distribution (Small vs. Large Business)
- Interactive filters for Business Size and State

### Page 2: Contractor Deep Dive
- Detailed Contractor Table with Obligations, Contract Count, and Average Contract Value
- Top 10 Industries (NAICS) by Obligations
- Product/Service Category Treemap
- Interactive filters for Business Size and State

## Key Insights

1. **Market Dominated by Major Primes**: Lockheed Martin leads with $12.5B (12% of total), followed by Raytheon ($3.8B), BAE Systems ($2.3B), and Northrop Grumman ($2.1B)

2. **Contract Size Varies Dramatically**: Lockheed Martin averages $9.57M per contract, while ECC Constructors averages $20.2M—showing different contracting strategies

3. **Small Business Goal Gap**: Only 25.12% of obligations go to small businesses, slightly above the federal 23% goal but indicating room for small business growth

4. **Geographic Concentration**: Texas leads ($18B+), followed by Virginia, Alabama, California, and Florida—reflecting major Army installation locations

5. **Guided Missiles Dominate**: Largest spending category, followed by Support Services (Engineering/Logistics), Aircraft, Combat Vehicles, and Ammunition

6. **Diverse Industry Mix**: Top industries include Guided Missile Manufacturing, Commercial/Institutional Building Construction, Engineering Services, and Ammunition Manufacturing

## Dashboard Preview

### Contract Overview
![Contract Overview](/contract_overview.png)

### Contractor Deep Dive
![Contractor Analysis](/contractor_analysis.png)

## Technical Details

**Tools Used:**
- Microsoft Power BI Desktop
- Power Query (data cleaning & transformation)
- DAX (Data Analysis Expressions)

**Data Processing:**
- Reduced 200+ columns to 13 essential fields
- Cleaned and renamed columns for readability
- Processed 127,000+ rows efficiently

**DAX Measures Created:**
```dax
Total Obligations = SUM(Contracts[Obligation Amount])

Total Contracts = COUNTROWS(Contracts)

Avg Contract Value = DIVIDE([Total Obligations], [Total Contracts], 0)

Unique Contractors = DISTINCTCOUNT(Contracts[Contractor])

Small Business Obligations = CALCULATE([Total Obligations], Contracts[Business Size] = "SMALL BUSINESS")

Small Business % = DIVIDE([Small Business Obligations], [Total Obligations], 0)
```

## Relevance to Tampa Market

This analysis is particularly relevant to the Tampa Bay defense market:
- **MacDill AFB** hosts CENTCOM and SOCOM
- **Florida ranks #5** in Army contract performance locations
- Major defense contractors (Lockheed, Raytheon, General Dynamics) have Tampa-area presence
- Growing demand for cleared IT professionals and analysts

## How to Use

1. Download the `.pbix` file
2. Open with Power BI Desktop (free from Microsoft)
3. Use Business Size slicer to compare small vs. large business contracts
4. Use Performance State slicer to analyze specific geographic markets
5. Click on any visual to cross-filter the dashboard

## Future Enhancements

- Add multi-year comparison (FY2023-2025)
- Include all DoD branches (Navy, Air Force, Marines)
- Add contract vehicle analysis (IDIQ, BPA, etc.)
- Build contractor win-rate analysis
- Add geographic map visualization

## Author

**David Chirino**  
Data Analyst | Tampa, FL  
