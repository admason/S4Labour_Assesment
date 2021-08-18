# S4Labour_Assesment
Data analyst Assesment
S4labour Data Exercise
Submitted by Adam Mason

Anonymised customer sales data 

This data was taken from the till links at the sites run by our customers. 
There is no validation of the data - it is as it was collected every evening. 
An organisation runs one or more sites. A site could be anything from a country gastro-pub to an urban wet-led pub. 

Questions 
1.	 Produce some descriptive statistics for the data. 
2.	 What can you see that looks odd? What would you recommend doing about it? 
3.	 Report the like for like sales by organisation and site by month for March 2019 and March 2021. 
4.	Which organisations have most sites? 



Responses:
1.	Descriptive statistics, obtained by use of Python 3 in jupyter notebook.
Top5 ActualSalesValue are all under Organisation ID:228, spread over the sites 1467, 1477 and 1448.


 [![1.jpg](https://i.postimg.cc/QdWmB680/1.jpg)](https://postimg.cc/cv0w2B8n)

Analysis by OrganisationID

 
The Organisation ID = 228 produced the maximum ActualSalesValue of £93309 at Site_ID 1467, which occurred on 16-March_2019.

Statistical Analysis by Org_ID:
 

Maximum sales for each Organisation found by the code:
m=dfAll.groupby('OrganisationID')['ActualSalesValue','tbl_ActualSales.PhysicalSiteID','Type'].max()

 


Analysis by Physical site ID:
 
Statistical Analysis by Physical Site_ID:
(The first 5 rows included here)
 

Maximum Sales for each physicalsite ID:
 
The full list can be viewed by using the code:
n=dfAll.groupby('tbl_ActualSales.PhysicalSiteID')['ActualSalesValue','Type','OrganisationID']
n.max()


2.	It appears unusual that a large portion of Actual Sales Values are negative.
The basics statistics for the data report that the minimum ActualSalesValue is -£3004, making the 1st and 2nd quartile to be zero.
Could these be due to prepaid booking for accommodation, meals or drinks, for example paid by companies for business visits/events?
If so, the data could be split into positive Sales, or the absolute value for all ActualSalesValues taken into account.

 


4, 
The Organisation_Id with the most physical sites is "882"

The list of PhysicalSiteID for all sites under the Organisation_ID 88 is:
 
 [ 465  492  493  494  495  496  497  498  499  500  501  502  503  504
  505  506  507  508  509  510  511  512  513  514  515  516  517  518
  521  522  523  524  525  527  528  529  531  532  533  534  535  536
  537  539  550  572  610  612  649  828  829  923  975 1058 1080 1159
 1200 1414 1574 1714 1715 1716 1718 1759 1774 1808 1826  491 1642 1854
 1938 1939 1940 1941 1942 1943 1944 1946 1947  438 1945  530 1937 2336
 2001 2489 2064 2095]


Please see description of the process












Description for analysis:
The original data set Database5 was opened in Microsoft Access, whereby the files ‘tbl_ActualSales’ and ‘tbl_PhysicalSites’ were joined by the key column of ‘PhysicalSiteID’. 
Also, the WorkDate field was drilled down to extract only sales which occurred during March 2019 AND March 2021.	
The table of 103295 rows was too large for use in Excel, so was split into two csv files, one for March 2019 and another for March 2021.

 
The resultant tables were extracted as csv files for use in Excel and Python.
March_2019_CSV
March_2021_CSV

The following Python code (IPYNB file) was used to extract the Descriptive Statistics:
S4Labour IPYNB File.
Or read the code in the S4Labour.PDF.
All included in the attached file.


