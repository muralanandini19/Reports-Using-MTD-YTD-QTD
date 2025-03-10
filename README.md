                    REPORTS USING MTD,YTD,QTD



Dashboard Link :https://app.powerbi.com/groups/me/reports/be037bb5-d810-4b86-97d6-6aa9a17ca559/cff1d5c74a38f82509e7?experience=power-bi



Procedure:

1.	Importing the Dataset:
	Launch Power BI Desktop.
	Click on "Get Data" in the Home tab of the ribbon.
	Select the appropriate data source option "Excel” and follow the prompts to import yoursample dataset into Power BI.

2.	Insert Rectangle Shape:




o	Click on “Format tab” on right side and perform changes on visual.
o	Shape > Style > #E66C37
o	Shape > Text >Text = “Page1” , Font Size = 46, Horizontal Alignment = “Center”.
 


3.	Create table:
	Home > Enter data > Create table by giving values to the columns
	Visualizations >Columns>orderDate>Quantity>mtd item quantity
	Click on new measure>and enter the below dax formula:
Mtd item qty = TOTALMTD(SUM(Orders[Quantity]),Orders[Order Date].[Date])

4.	Create table:
	Home > Enter data > Create table by giving values to the columns
	Visualizations >Columns>orderDate>Quantity>qtd item quantity
	Click on new measure>and enter the below dax formula:
qtd item qty = TOTALQTD(SUM(Orders[Quantity]),Orders[Order Date].[Date])

5.	Create table:
	Home > Enter data > Create table by giving values to the columns
	Visualizations >Columns>orderDate>Quantity>ytd item quantity
	Click on new measure>and enter the below dax formula:
Ytd item qty = TOTALYTD(SUM(Orders[Quantity]),Orders[Order Date].[Date])


6.	Create table:
	Home > Enter data > Create table by giving values to the columns
	Visualizations >Columns>orderDate>Total Mtd Orders
	Visualizations >Columns>orderDate>Total qtd Orders
	Visualizations >Columns>orderDate>Total ytd Orders
	Click on new measure>and enter the below dax formula:
Total Mtd Orders = TOTALMTD(Count(Orders[Order ID]),Orders[Order Date].[date]) Total Qtd Orders = TOTALQTD(Count(Orders[Order ID]),Orders[Order Date].[date]) Total Ytd Orders = TOTALYTD(Count(Orders[Order ID]),Orders[Order Date].[date])

7.	Create table:
	Home > Enter data > Create table by giving values to the columns
	Visualizations >Columns>orderDate>profit>mtdProfit
	Click on new measure>and enter the below dax formula:
MTDprofit = CALCULATE(sum(Orders[Profit]),DATESMTD(Orders[Order Date].[Date]))


8.	Create table:
	Home > Enter data > Create table by giving values to the columns
	Visualizations >Columns>orderDate>profit>qtdProfit
	Click on new measure>and enter the below dax formula:
QTDprofit = CALCULATE(sum(Orders[Profit]),DATESQTD(Orders[Order Date].[Date]))
 

9..Create table:
	Home > Enter data > Create table by giving values to the columns
	Visualizations >Columns>orderDate>profit>ytdProfit
	Click on new measure>and enter the below dax formula:
YTDprofit = CALCULATE(sum(Orders[Profit]),DATESYTD(Orders[Order Date].[Date]))


 
10. Final Output


![Image](https://github.com/user-attachments/assets/21251e0d-fb56-4721-baa8-b04e444475df)
