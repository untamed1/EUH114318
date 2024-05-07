# EUH114318
Excel Worksheet to OData with Params
Provided for EpiUser.help
https://www.epiusers.help/t/excel-parameter-to-filter-epicor-baq/114318/25

Simple BAQ: zzzEUH
/*
 * Disclaimer!!!
 * This is not a real query being executed, but a simplified version for general vision.
 * Executing it with any other tool may produce a different result.
 * Defined Parameter: Co nvarchar(8)
 */
 
select 
	[Company].[Company] as [Company_Company],
	[Plant].[Plant] as [Plant_Plant],
	[Plant].[Name] as [Plant_Name],
	(Company.Company+'|'+Plant.Plant) as [Calculated_CoSite]
from Erp.Company as Company
inner join Erp.Plant as Plant on 
	Company.Company = Plant.Company
where (Company.Company like @Co)
