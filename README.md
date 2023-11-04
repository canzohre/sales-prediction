                                                   SALES FORECAST WITH TIME SERIES ANALYSIS

In this project, the sales of the sales personel in the following months are estimated by using a SQL table in which includes the transaction of all sales personel.

In addition to estimating the number of all sales made by the sales personnel in the desired month, sales in certain situations are also estimated by using the information of the delivery point where the transaction was made and the information of the people to whom the sale was made.

For example, based on the sales made by a certain salesperson to a certain customer, it is analyzed how much sales he can make to that customer in the following month. The same principle  can be applied to a certain delivery point.

Functions in the Project and their simple explanations:

•	Connection between python and mssql server was established using the pyodbc library

•	found_sales_in(Month,Year,sid,operation_code,*args) : This function first asks the user for an operation code. Meaning of the operation code is if the user wants to predict the salesperson's total number of sales in the following months, the operation code is 1; If the user wants to predict the number of sales the salesperson will make to a certain buyer in the following months, operation code 2; If the user wants to predict the number of sales that the salesperson will make from a certain point of delivery  next, he enters the operation code as 3. According to the entered operation code, the sales number of the salesperson on the entered date is returned as a parameter. This function was created to be used in the  All_sales_month_by_month().


•	increase_date : This function has been created also to be used in All_sales_month_by_month function.When  called it increment the date  by one month.

•	All_sales_month_by_month() :  This function returns sales number of a salesman month by month as a dataframe according to operation code which has been entered.


•	sales_forecast() : This function performs time series analysis on the dataframe returned by the All_sales_month_by_month() function, predicts the sales numbers month by month until the date entered by the user, and returns the predictions as a dataframe.

Here program asks required parameters like ıd of a sales person , operation code and the date:

![Ekran görüntüsü 2023-11-04 225825](https://github.com/canzohre/sales-prediction/assets/79839937/f23bad9a-5f38-4f16-b1f6-ce9661eb12f8)



Then making predictions month by month until date become equals with the date which user entered:

![Ekran görüntüsü 2023-11-04 225803](https://github.com/canzohre/sales-prediction/assets/79839937/73eed404-a727-4c2d-a1fd-d9abbdf57098)




There is a sales number of a sales person month by month:


![Ekran görüntüsü 2023-11-04 225853](https://github.com/canzohre/sales-prediction/assets/79839937/db6e5697-9c55-4108-8f1a-aa58b5fadc04)




And there is a graph which visualise forecasts and and sales number before starting forecasting to see model actually can catch the patterns:

![Ekran görüntüsü 2023-11-04 225908](https://github.com/canzohre/sales-prediction/assets/79839937/e55a0c66-26b5-4b8a-a0d8-a1abb3c05cf6)

Since the amount of data has not sufficient for this kind of task model could be unaccurate for some sales person.Data augmentation techniques can be applied to overcome this situation.
