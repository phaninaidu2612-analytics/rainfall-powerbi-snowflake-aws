# Agriculture Rainfall & Yield Analysis Dashboard | Power BI | Snowflake | AWS

## Dashboard Link

https://app.powerbi.com/view?r=eyJrIjoiZmZiYTY1ZmEtZjVjOC00ODgwLTkzYmEtNWE4MWIwYzBhMzBmIiwidCI6IjA2Y2Q0ZWQ1LTNiN2YtNDdiMC04ZWY2LTI5ZGVlMWM1MDYwYiJ9&pageName=6cb922dd89798b6bfa2f

## Dashboard Preview

![d1](https://github.com/user-attachments/assets/b2912330-d24a-4484-8e14-9c578c48fc0c)

![d2](https://github.com/user-attachments/assets/85eb98a1-f9f7-4f65-ad8a-02f5a9ecb4f9)

![d3](https://github.com/user-attachments/assets/0df30d1b-ff5e-4f7e-b1c3-f357afdcb17f)

![d4](https://github.com/user-attachments/assets/30c11d0a-8558-4c87-909f-96e8813d459b)



## Problem Statement

This project focuses on analyzing agricultural and environmental factors such as:

- Rainfall
- Temperature
- Humidity
- Crop Yield

The objective of the dashboard is to understand how climatic and environmental conditions influence agricultural productivity across different:

- Seasons
- Crops
- Locations
- Irrigation types
- Soil categories

The dashboard helps stakeholders and agricultural analysts identify crop performance trends and environmental patterns for better agricultural planning and decision-making.

## Data Source & Cloud Integration

The project follows a cloud-based analytics workflow using:

- AWS S3
- Snowflake
- Power BI

### AWS & Snowflake Integration Workflow
-  AWS Setup:

    Created an S3 Bucket and uploaded the agriculture Excel dataset
    Configured AWS IAM Roles & Policies for secure access

    ![aws](https://github.com/user-attachments/assets/b9dfc033-3782-4744-ae1c-200e846c4548)

    ![aws1](https://github.com/user-attachments/assets/d54cd34b-31a7-475b-aab0-3cfaaf8a6019)


-  Snowflake Integration :

    Created a Snowflake Warehouse
    Integrated AWS S3 with Snowflake
    Established secure cloud connectivity
    Imported agricultural data from AWS into Snowflake tables

    ![snowflake](https://github.com/user-attachments/assets/23e7c3c6-0547-4f57-b26c-c03afdb87625)
- Power BI Integration :

    Connected Power BI with Snowflake
    Imported transformed agricultural data into Power BI for analysis and visualization

    ![pbi](https://github.com/user-attachments/assets/c533a085-10a8-40e9-ad39-dbfda3770ac3)

## Dataset Description

The dataset contains agriculture and environmental-related metrics.

Columns Included:

- Year
- Location
- Area
- Rainfall
- Temperature
- Soil Type
- Irrigation
- Yields
- Humidity
- Crops
- Price
- Season

## Data Cleaning & Feature Engineering (Snowflake SQL)

Performed data transformation and feature engineering directly in Snowflake using SQL.

- Rainfall Adjustment :

    update agriculture
    set rainfall = 1.1 * rainfall
- Area Adjustment :

    update agriculture
    set area = 0.9 * area
- Year Group Feature Engineering :
    ```sql
    alter table agriculture
    add year_group string;
    ```
    ```sql
    update agriculture
    set year_group = 
    case
         when year between 2004 and 2009 then 'Y1'
        when year between 2010 and 2015 then 'Y2'
        else 'Y3'
    end
    ```
- Rainfall Group Categorization
    ```
    alter table agriculture
    add rainfall_group string;
    update agriculture
    set rainfall_group = 
    case 
        when rainfall >= 255 and rainfall < 1200 then 'Low'
        when rainfall >= 1200 and rainfall < 2800 then 'Medium'
        else 'High'
    end
    ```
## Dashboard Features

The dashboard includes four major analytical sections:

 **Rainfall Analysis** **:**

    Average Rainfall by:
    - Year
    - Season
    - Crops
    - Location

**Temperature Analysis** **:**

    Average Temperature by:
    - Year
    - Season
    - Crops
    - Location

**Humidity Analysis** **:**

    Average Humidity by:
    - Year
    - Season
    - Crops
    - Location

**Yield Analysis** **:**

    Average Yield by:
    - Year
    - Season
    - Crops
    - Location

## Interactive Features
- Dynamic slicers for
    Irrigation
    Soil Type
    Interactive filtering across all visuals


- Comparative environmental analysis across seasons and locations.
- Implemented Navigator Bars for seamless page-to-page navigation from the introduction dashboard
Enabled user-friendly navigation between:
- Rainfall Analysis
- Temperature Analysis
- Humidity Analysis
- Yield Analysis pages


![nav](https://github.com/user-attachments/assets/478db751-c8d9-449f-b3e1-3760c50fd184)

## Key Insights
**Rainfall Insights:**
Locations such as Bangalore, Raichur, and Kasaragodu receive comparatively higher rainfall levels.
Crops like Paddy, Arecanut, and Cardamom require higher rainfall conditions for better productivity.
Seasonal rainfall remains relatively consistent across:
Rabi
Kharif
Zaid

**Temperature Insights:**
Higher temperatures are observed in:

    - Bangalore
    - Davangere
    - Raichur
    Crops such as:
    - Ginger
    - Tea
    - Cashew

perform well under comparatively higher temperature conditions.
Kharif and Zaid seasons experience higher average temperatures than Rabi.

**Humidity Insights:**
Humidity levels remain relatively stable across seasons and locations.
Crops such as:
- Cotton
- Pepper
- Paddy

show strong adaptability to higher humidity conditions.

**Yield Insights :**
Cotton and Coconut generate the highest agricultural yield among all crops analyzed.
Locations such as:
- Kodagu
- Mysuru
- Madikeri

demonstrate stronger yield performance.

Rabi season contributes the highest average yield compared to Kharif and Zaid.
 
## Business & Agricultural Impact :

The dashboard helps:

- Analyze crop productivity trends
- Understand environmental impact on agriculture
- Compare seasonal agricultural performance
- Support irrigation and crop planning decisions
- Improve yield forecasting and agricultural strategy planning
 
## Tools & Technologies Used :
- Power BI Desktop
- Snowflake
- AWS S3
- AWS IAM
- SQL
- Power Query
- Data Visualization & Analytics

## Conclusion

This project demonstrates a complete cloud-based agricultural analytics workflow involving:

- AWS S3 cloud storage
- Snowflake data warehousing
- SQL-based feature engineering
- Power BI dashboard development

The dashboard provides valuable environmental and agricultural insights that support data-driven farming and crop management strategies.
