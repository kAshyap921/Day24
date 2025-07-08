// 1. CALCULATE with filter modification
Online_Sales = CALCULATE(SUM(Sales[Amount]), Sales[Channel] = "Online")

// 2. FILTER with RELATED
West_Coast_Customers = 
FILTER(
    Customer,
    RELATED(Location[Region]) = "West Coast"
)

// 3. SUMX with row context
Total_Profit = 
SUMX(
    Sales,
    (Sales[UnitPrice] - RELATED(Product[UnitCost])) * Sales[Quantity]
)
