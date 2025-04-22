## 📋 Data Dictionary

| Table                | Column           | Type                         | Description                                                      |
|----------------------|------------------|------------------------------|------------------------------------------------------------------|
| **CustomerTable**    | Customer ID      | Text                         | Unique identifier for each customer                              |
|                      | Customer Name    | Text                         | Full name of the customer                                        |
|                      | Segments         | Text                         | Customer segment (“Consumer” / “Corporate” / “Home Office”)      |
| **DateDimension**    | Date             | Date                         | Calendar date                                                    |
|                      | Year             | Whole Number                 | Calendar year (e.g. 2017)                                        |
|                      | Month            | Whole Number                 | Month number (1–12)                                              |
|                      | Quarter Number   | Whole Number                 | Quarter of year (1–4)                                            |
|                      | Day              | Whole Number                 | Day of month (1–31)                                              |
|                      | Day of Week      | Text                         | Name of weekday (e.g. Monday)                                    |
| **FactSales**        | Row ID           | Whole Number                 | Surrogate key for each fact row                                  |
|                      | Order ID         | Text                         | Business order identifier                                        |
|                      | Order Date       | Date                         | Date when the order was placed                                   |
|                      | Ship Date        | Date                         | Date when the order was shipped                                  |
|                      | Ship Mode        | Text                         | Shipping method (Standard, First Class, etc.)                    |
|                      | Customer ID      | Text                         | FK → CustomerTable.Customer ID                                   |
|                      | Product ID       | Text                         | FK → ProductDimension.Product ID                                 |
|                      | Location ID      | Whole Number                 | FK → LocationDimension.Location ID                               |
|                      | Sales            | Decimal (USD)                | Gross revenue amount                                             |
|                      | Profit           | Decimal (USD)                | Profit amount                                                    |
|                      | Quantity         | Whole Number                 | Number of units sold                                             |
|                      | Discount         | Decimal (Percentage)         | Discount rate applied (e.g. 0.2 = 20 %)                          |
| **LocationDimension**| Location ID      | Whole Number                 | Surrogate key for each location                                  |
|                      | City             | Text                         | City name                                                        |
|                      | State            | Text                         | State or province name                                           |
|                      | Country          | Text                         | Country name                                                     |
|                      | Region           | Text                         | Geographic region (e.g. Central, East, South, West)              |
|                      | Postal Code      | Whole Number                 | Postal (ZIP) code                                                |
| **ProductDimension** | Product ID       | Text                         | Unique identifier for each product                               |
|                      | Product Name     | Text                         | Descriptive product name                                         |
|                      | Category         | Text                         | High‑level category (Technology, Furniture, Office Supplies)     |
|                      | SubCategory      | Text                         | More granular category (e.g. Phones, Chairs, Binders)            |
