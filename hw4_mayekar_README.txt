1.  Converted csv files of four tables provided for capstone project
2.  Input Data => four csv files

Sales_week table 

Datatime tool => Converted "Date" column to date data type with new column "Start Date"
Multifield formula => Added "w" in week0 column
Multifield formula => Added new filed for End date
Multifirld formula => Added Quarter inplace of quarter number

Sales_history table

Transpose => transpose weekly quantity in tabular format 
Filter => removed all records with "0" quantities
Select => fixed column alias as  required for final output and fixed datatype to use min memory


Sales Team

TextToColumn => Split "Sales Team Lead" column to firstname and latname 
DataCleansing => Removed leading space from FirstName 
AutoField   => fixed data types and column sizes
select => removed sales team lead and isfound column

Sales_product
	Product_code table
	---------------
	Transpose => converted product table in tabular format to get price of each quarter for the given item code
	AutoField => fixed column sizes and datatypes
	select  => prodcut code information with correct alias

	ESP_code table
	--------------
	AutoField => fixed column sizes and datatypes
	select  => ESP information selected from product table


Joins
------

Join1 : Sales_week  and Sales_history table on  (W# and Sales_year)
Join2 : Join1 and Sales_team table on (empID)
Join3 : Join2 and prod_code on (ItemCode and Sales_quarter)
Join4 : Join2 and ESP_code on (ItemCode)

Question1 Demo
-------------
Merge tool => Join3 + Join4
Multifield formual => calculate total price (Qty * price)
datetime tool => convert start and end date to String and correct Alias
select => Question1 final output with the correct column order and names


Question 3
----------
Multifield formula => calculate total price (Qty * price) for ESP records
select => Question3 final output with the correct column order and names


Summary of ESP_CODE
------------------
Summarize => Group by ESP_CODE,price (sum of Qty and sum of ESP_total$)
Summarize => Summarize ESP_total$ 













 