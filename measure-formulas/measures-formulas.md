Average Discount =
AVERAGEX(
    FactSales,
    FactSales[Discount]
)

Average Sales =
AVERAGEX(
    FactSales,
    FactSales[Total Sales]
)

Consumer Customer Count =
CALCULATE(
    DISTINCTCOUNT(CustomerTable[Customer ID]),
    CustomerTable[segmets] = "consumer"
)

Corporate Customer Count =
CALCULATE(
    DISTINCTCOUNT(CustomerTable[Customer ID]),
    CustomerTable[segmets] = "Corporate"
)

Customer Count =
DISTINCTCOUNT(CustomerTable[Customer ID])

HomeOffice Customer Count =
CALCULATE(
    DISTINCTCOUNT(CustomerTable[Customer ID]),
    CustomerTable[segmets] = "Home Office"
)

MTD Profit =
TOTALMTD(
    FactSales[Total Profit],
    DateDimension[Date]
)

MTD Quantity =
TOTALMTD(
    FactSales[YTD Quantity],
    DateDimension[Date]
)

MTD Sales =
TOTALMTD(
    FactSales[YTD Sales],
    DateDimension[Date]
)

Profit Last Year =
CALCULATE(
    FactSales[Total Profit],
    SAMEPERIODLASTYEAR(DateDimension[Date])
)

Profit Margin =
DIVIDE(
    FactSales[Total Profit],
    FactSales[Total Sales]
)

Profit Margin Variance =
FactSales[Profit Margin] -
CALCULATE(
    FactSales[Profit Margin],
    SAMEPERIODLASTYEAR(DateDimension[Date])
)

QTD Profit =
TOTALQTD(
    [Total Profit],
    DateDimension[Date]
)

QTD Sales =
TOTALQTD(
    FactSales[Total Sales],
    DateDimension[Date]
)

Sales Growth % =
DIVIDE(
    FactSales[Total Sales] - FactSales[Sales Last Year],
    FactSales[Sales Last Year]
)

Sales Last Year =
CALCULATE(
    FactSales[Total Sales],
    SAMEPERIODLASTYEAR(DateDimension[Date])
)

Total Discount Amount =
SUMX(
    FactSales,
    FactSales[Sales] * FactSales[Discount]
)

Total Profit =
SUM(FactSales[Profit])

Total Quantity =
SUM(FactSales[Quantity])

Total Sales =
SUM(FactSales[Sales])

YTD last year =
CALCULATE(
    [YTD Sales],
    SAMEPERIODLASTYEAR(DateDimension[Date])
)

YTD Profit =
TOTALYTD(
    FactSales[Total Profit],
    DateDimension[Date]
)

YTD Quantity =
TOTALYTD(
    FactSales[Total Quantity],
    DateDimension[Date]
)

YTD Sales =
TOTALYTD(
    FactSales[Total Sales],
    DateDimension[Date]
)
