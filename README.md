# OLAP-Data-Warehouse

This Capstone Highlights a DataWarehouse and the work it takes to have enough clean data to be able to author it in Power BI.  I extracted a back up file provided by Microsoft's Business Scenario github page.  From this back up file I created 2 more databases for the staging layer.  In the Staging and Datawarehouse Databases, I identified the Fact and Dimension tables.  After Joining and Cleaning the tables I leveraged SQL Server Integration Services to load the Source to the Staging layer and from the Staging layer to the Datawarehouse. To execute all the packages at once, I created two Control Packages. Inside the AWN_SSAS folder, there is a solution where the Tabular Model is created, this model is loaded into SQL Server Management Studio for Analyzing and loaded into Power BI.
In a Real world scenario the DataBase will be located off site somewhere, the staging layer and the Datawarehouse would also be created off site as well. Only indiviuals with the correct authority and credentials will have access to the data to query.


## **FEATURES**

_1_: Set up a local database and read data with SQL Server Management Studio (SSMS)

_2_: Merge and join.  Data is cleaned and read in from a DataWarehouse, the DW is created from a Staging Layer that consists of 3 databases, a backup file from Microsoft's AdventerWorks Business Case Study (AdventureWorks2014.bak) and two other databases created from the different tables pulled and joined from the AdventureWorks2014 back up file.

_3_: Make an Interactive Power BI dashboard to display the data.  After creating and joining the products tables I created 2 dash boards:
    Total Sales by Region and Total Sales by Inventory.

_4_: Utilizing Visual Studio's Integration Services (SSIS) to update and populate the tables in SqL Server Management Studio (SSMS)


<details>

<summary>Special instructions required for the Reviewer:</summary>



**•** To View the Power BI file (TotalSalesby Inventory and Region.pbix), 
you must have Power BI downloaded and installed on your computer:
`https://powerbi.microsoft.com/en-us/downloads/`

If you choose to not download Power BI you can reference the dashboard from the attached .pdf file but it will not have the interactive options.

#

**•** To Extract and view the AdventureWorks2014.bak file, you will need to download and install both SQL Server 2022 and SqL Server Management Studio (SSMS):

`https://info.microsoft.com/ww-landing-sql-server-2022.html?culture=en-us&country=us`

`https://marketplace.visualstudio.com/items?itemName=SSIS.MicrosoftDataToolsIntegrationServices`

Once your done installing SQL Sever put the AdventureWorks2014.bak file in the folder:

`C:\Program Files\Microsoft SQL Server\MSSQL16.MSSQLSERVER\MSSQL\Backup`

Once you've relocated the AdventureWorks2014.bak, open SqL Server Management Studio (SSMS).

In your `Object Explorer` tab, press the connect button and a dialog box will pop up, its called connect to server (SQL Server), 

for your Server name type `localhost` and connect.

After you've connected to your Server, expand the tree and right click the `Databases` folder, 

choose `Restore Database...` at the `Destination` option click the drop down arrow and choose `AdventureWorks2014`.

#

**•** To Create the other two databases (AWN_STG.sql and AWN_DW.sql):
Locate the scripts folder, inside there are 3 SQL script, load them into SqL Server Management Studio (SSMS) and `Execute` them by clicking the Play button or by pressing 
(ALT + X). the 3rd script (AWN_HR.sql) if you execute it the HR Fact tables will be created in the staging area, it will also Create views and than retrive data from the source, this script tells me how much the emplyees are getting paid.

#

**•** To view the DataWarehouse, AWN_DW, and AWN_SSAS solution files you will need to install the SSIS extensions and the data Tools for Visual Studio:
`https://marketplace.visualstudio.com/items?itemName=SSIS.MicrosoftDataToolsIntegrationServices`

For the data Tools:
Open Visual Studio Installer, click `Modify` button, 

Scroll down to `Other Toolsets`, 

Select `Data storage and processing`, than click Modify

Once your done installing, open the solutions located in their respective folder. You will have to reroute all the DataBase connections:

In the Solution Explorer double click the Connection Managers and direct it to your localhost by typing a Period `.` in the `Server Name` field, below that in 
`connect to a database` click the dropdown menu and locate the database, do this for all 3 databases.


</details>

## **Speical Thanks to :** Analytics with Nags and my Mentors at Code Kentucky