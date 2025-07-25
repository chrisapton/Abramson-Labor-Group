# AdventureWorksLT2022 Sales Report Demo

This repository contains a demonstration of a basic database-to-report workflow using Microsoft SQL Server Express, the AdventureWorksLT2022 sample database, and Power BI Desktop.

## Project Overview

The goal of this project is to showcase end-to-end data handling, from restoring a commercial sample database to a local SQL Server instance, connecting Power BI Desktop, and creating a concise, interactive sales report with multiple visuals and filters. This work was presented to the managers at the Abramson Labor Group.

## Contents

* `LICENSE`
  Standard repository license file.
* `Christopher_Apton_Sales_Report_AdventureWorks.pbix`
  Power BI Desktop file containing the completed report and all relevant DAX logic and visuals.
* `AdventureWorksLT2022.bak`
  SQL Server database backup of the AdventureWorksLT2022 sample, as downloaded from [Microsoft Learn](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure).

## Steps & Tools Used

1. **Database Setup**

   * Installed [Microsoft SQL Server Express](https://www.microsoft.com/en-us/sql-server/sql-server-downloads).
   * Restored the `AdventureWorksLT2022.bak` database using SQL Server Management Studio (SSMS) or equivalent.

2. **Data Connection**

   * Connected Power BI Desktop to the local SQL Server instance.
   * Imported relevant tables and relationships from AdventureWorksLT2022.

3. **Report Development**
   The report is designed as a one-page sales dashboard and includes:

   * **Two Filters (Slicers):**

     * *Sales Year*
     * *Sales Status*
   * **Pie Chart:**

     * Visualizes total sales amount by territory for the selected year.
   * **Matrix:**

     * Breaks down sales by territory and salesperson, with sales status as columns.
   * **Card Visual:**

     * Displays average sales per salesperson per territory.
     * Utilizes a DAX measure:

       ```DAX
       Average Sales Per Salesperson Per Territory = 
         DIVIDE([Total Sales], [Number of Salespersons])
       ```
   * All visuals are interactive, so selecting data in one visual filters the others as expected in Power BI.

## How to Use

1. Restore the AdventureWorksLT2022 database on a local SQL Server instance (see [Microsoft's instructions](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure)).
2. Open the `.pbix` file in Power BI Desktop.
3. Update the data source connection in Power BI to point to your local SQL Server instance.
4. Interact with the report using the provided slicers and visuals.

## Notes

* The `.pbix` file contains all necessary DAX measures and report formatting.
* Data is based on the AdventureWorksLT2022 sample and can be freely redistributed for learning and demo purposes.
