# 📊 Data Dictionary

## Overview
This document provides detailed information about all data fields, tables, and relationships used in the Dynamic Market Sales Analysis dashboard.

## 📋 Table Structure

### 1. Sales Data (`sales_data.xlsx`)

| Field Name | Data Type | Description | Example Values | Constraints |
|------------|-----------|-------------|----------------|-------------|
| `OrderID` | String | Unique identifier for each sales order | ORD-001, ORD-002 | Primary Key, Not Null |
| `OrderDate` | Date | Date when the order was placed | 2024-01-15 | YYYY-MM-DD format |
| `CustomerID` | String | Unique identifier for customers | CUST-001, CUST-002 | Foreign Key |
| `ProductID` | String | Unique identifier for products | PROD-001, PROD-002 | Foreign Key |
| `ProductName` | String | Name of the product | Gaming Laptop, Wireless Mouse | Max 100 characters |
| `Category` | String | Product category | Laptops, Accessories, Components | Controlled vocabulary |
| `Brand` | String | Product brand | Dell, HP, Logitech, AMD | Max 50 characters |
| `Quantity` | Integer | Number of units sold | 1, 2, 5 | Positive integers only |
| `UnitPrice` | Decimal | Price per unit | 999.99, 25.50 | Currency format |
| `TotalPrice` | Decimal | Total order amount | 1999.98, 51.00 | Calculated field |
| `Discount` | Decimal | Discount percentage applied | 0.10, 0.15 | 0-1 range |
| `SalesChannel` | String | Channel through which sale was made | Online, Retail, B2B | Controlled vocabulary |
| `Region` | String | Geographic region | North America, Europe, Asia | Controlled vocabulary |
| `SalesRep` | String | Sales representative name | John Smith, Jane Doe | Employee names |

### 2. Product Catalog (`product_catalog.csv`)

| Field Name | Data Type | Description | Example Values | Constraints |
|------------|-----------|-------------|----------------|-------------|
| `ProductID` | String | Unique product identifier | PROD-001, PROD-002 | Primary Key |
| `ProductName` | String | Product name | Dell XPS 13, Logitech MX Master | Max 100 characters |
| `Category` | String | Product category | Laptops, Mice, Keyboards | Hierarchical |
| `SubCategory` | String | Product subcategory | Gaming Laptops, Wireless Mice | Child of Category |
| `Brand` | String | Product brand | Dell, Logitech, AMD, Intel | Max 50 characters |
| `Model` | String | Product model | XPS 13, MX Master 3 | Max 50 characters |
| `LaunchDate` | Date | Product launch date | 2023-06-15 | YYYY-MM-DD format |
| `Cost` | Decimal | Product cost | 500.00, 30.00 | Currency format |
| `MSRP` | Decimal | Manufacturer suggested retail price | 999.99, 79.99 | Currency format |
| `InStock` | Boolean | Stock availability | TRUE, FALSE | Boolean values |
| `Warranty` | Integer | Warranty period in months | 12, 24, 36 | Positive integers |

### 3. Customer Data (`customer_data.csv`)

| Field Name | Data Type | Description | Example Values | Constraints |
|------------|-----------|-------------|----------------|-------------|
| `CustomerID` | String | Unique customer identifier | CUST-001, CUST-002 | Primary Key |
| `CustomerName` | String | Customer full name | John Smith, Acme Corp | Max 100 characters |
| `CustomerType` | String | Type of customer | Individual, Business | Controlled vocabulary |
| `Email` | String | Customer email address | john@email.com | Valid email format |
| `Phone` | String | Customer phone number | +1-555-123-4567 | International format |
| `Address` | String | Customer address | 123 Main St, New York | Max 200 characters |
| `City` | String | Customer city | New York, Los Angeles | Max 50 characters |
| `State` | String | Customer state/province | NY, CA, TX | 2-letter codes |
| `Country` | String | Customer country | USA, Canada, UK | 3-letter ISO codes |
| `PostalCode` | String | Postal/ZIP code | 10001, 90210 | Various formats |
| `RegistrationDate` | Date | Customer registration date | 2023-01-15 | YYYY-MM-DD format |
| `Segment` | String | Customer segment | Premium, Standard, Basic | Controlled vocabulary |

## 🔗 Data Relationships

### Primary Relationships
```
Sales Data ──┐
             ├── CustomerID ──> Customer Data
             └── ProductID ──> Product Catalog

Date Dimension ──> OrderDate (Sales Data)
```

### Relationship Cardinality
- **Sales to Customer**: Many-to-One (M:1)
- **Sales to Product**: Many-to-One (M:1)
- **Sales to Date**: Many-to-One (M:1)

## 📊 Calculated Fields & Measures

### Key Measures (DAX)

#### Revenue Metrics
```dax
Total Revenue = SUM(SalesData[TotalPrice])

Revenue Growth % = 
DIVIDE(
    [Total Revenue] - CALCULATE([Total Revenue], PREVIOUSMONTH('Date'[Date])),
    CALCULATE([Total Revenue], PREVIOUSMONTH('Date'[Date])),
    0
) * 100

YTD Revenue = TOTALYTD([Total Revenue], 'Date'[Date])
```

#### Profitability Metrics
```dax
Total Profit = 
SUMX(
    SalesData,
    SalesData[Quantity] * (SalesData[UnitPrice] - RELATED(ProductCatalog[Cost]))
)

Profit Margin % = DIVIDE([Total Profit], [Total Revenue], 0) * 100

Average Order Value = DIVIDE([Total Revenue], DISTINCTCOUNT(SalesData[OrderID]))
```

#### Customer Metrics
```dax
Customer Count = DISTINCTCOUNT(SalesData[CustomerID])

New Customers = 
CALCULATE(
    [Customer Count],
    FILTER(
        CustomerData,
        CustomerData[RegistrationDate] >= STARTOFMONTH('Date'[Date])
    )
)

Customer Retention Rate = 
DIVIDE(
    [Returning Customers],
    [Total Customers Previous Period],
    0
) * 100
```

## 🎯 Business Rules & Validation

### Data Quality Rules
1. **Completeness**: All key fields must have values
2. **Consistency**: Category values must match predefined list
3. **Accuracy**: UnitPrice * Quantity should equal TotalPrice
4. **Timeliness**: OrderDate cannot be in the future
5. **Validity**: Email addresses must follow valid format

### Business Logic
- Discount cannot exceed 50%
- Quantity must be positive integer
- Order total must be greater than $0
- Customer must exist before order creation
- Product must be in stock for online orders

## 🔄 Data Refresh & Updates

### Refresh Schedule
- **Frequency**: Every 4 hours during business days (9 AM - 6 PM)
- **Weekend**: Once daily at 8 AM
- **Manual**: Available on-demand

### Data Sources
- **Primary**: Excel files uploaded to SharePoint
- **Secondary**: CSV exports from ERP system
- **Backup**: SQL Server database connection

### Update Process
1. Data validation checks
2. Error logging and notification
3. Incremental refresh for large datasets
4. Full refresh for master data
5. Dashboard cache refresh

## 📈 Performance Optimization

### Indexing Strategy
- Primary keys on all dimension tables
- Composite indexes on frequently filtered columns
- Date table optimized for time intelligence

### Data Model Optimization
- Star schema design
- Calculated columns minimized
- Proper data types assigned
- Relationships optimized for performance

---

*Last Updated: [Current Date]*
*Version: 1.0*
