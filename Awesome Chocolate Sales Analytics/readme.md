# Project 1: Awesome Chocolate🍫Power BI sales Analytics

---

**Goal:**  
Analyze chocolate sales performance across regions, products, and salespeople to understand **revenue, costs, and profitability**, and help management make better business decisions.

---

**Tools and Skills used in Project:**
1. Dashboard Design
2. DAX Measures
3. Time Intelligence 
4. KPI Kards
5. Reference Labels
6. Card Formating 
7. BookMarks
8. Tooltips
9. Field Paramets
10. Grouping
11. Zoom Slider 
12. Dynamic Trends
13. Table Design
14. Histogram Chart

---

**Now Load the Raw data with 5 Tables**

- **Fact Table**
  - `Shipment`
    - Contains transactional data for each shipment:
      - Sales
      - Boxes
      - Costs
      - Date Key
      - Product Key
      - Geography Key
      - Sales Person Key

- **Dimension Tables**
  - `Product` – Product name, category, subcategory, etc.
  - `Geography` – Region, country, city, etc.
  - `Sales Person` – Sales representative details.
  - `Calendar` – Date, month, quarter, year, etc.

Observe the Data Model and fix the relationship to the ones not connected. Need to make this as Star Schema with One to Many Relationship with Fact Table

For Calender Table, In the Model view, right click and mark it as "Date Table"

---

**Terminology used in Project:**
1. **Low box shipment** means boxes  less than 50 in count shiped

---

**KPI using DAX MEASURES** 
- Total Sales 
- Total Boxes
- Total Shipments 
- Total Cost
- Total Profit
- Profit Percentage
- LBS Count (Low Box Shipment Count)
- LBS %

---

Start with creating new table for "Measure"
Home > Enter Data > Give Table Name: _Measure and enter Load

Delete the by default column
and you will see, the Measure folder icon changes from "table" to calculator". This is because the Power BI understands that this is a Measure table having all the calculates values

**Now create Measure:**
1. **Total Sales** = sum(Shipment[Sales])
2. **Total Boxes** = Sum[Shipment[Boxes])
3. **Total Cost** = SUM(shipments[Costs])
4. **Total Profit** = total Sales - Total Profit 
5. **Profit %** = DIVIDE([Total Profit],[Total Sales])
6. **Total Shipments** = countrows(Shipment)
7. **LBS Count** = Calculate([total shipment], shipment[boxes]<50)
8. **LBS %** = DIVIDE([LBS Count],[Total Shipments])

---

Now, To Calculate Total Cost: 
Product Table: Cost per box and Product Name
Shipment Table: Boxed and Product Name

**Options to Calculate:**
Option_1: Create a New Calculated Column in Shipment Table (Easy Way) using "Related funtion" 
Total Cost for each Shipment = RELATED(products[Cost per box])*shipments[Boxes]
Option_2, 3 and 4: Dax Measure / SQL / Power Query

---

**Tip:** Do recheck all the calculated measures again at the top - to see what format it is i.e currency $ and %age

---

Now, Lets Calculate the Year by Year and Month by Month Changes for all Key Metrics in KPI Cards / Measure

To do this, Lets click on Home > Transform Data. This will open Power Query

Now click on "Add Column" > Date and then add new Year, Month, Month Name, Day of the Week, Day Name to the Table

Then Click on Home > "Close and Apply" 

---

Now, **Create a new Measure(s):**

**Total sales(Prev Month) =**
CALCULATE(
     [Total Sales],
     PREVIOUSMONTH('calendar'[Date]))
	 
	 
**MoM Change % =** 
     var this_month = [Total Sales]
     var prev_month = [Total sales(Prev Month)]
RETURN
    DIVIDE(this_month-prev_month,prev_month)
	
---

**Ref Sources:**
1. AC Project Dashboard https://www.youtube.com/watch?v=ooJO7NW4uJU&list=PLmejDGrsgFyBsZlhRBdJQb9dQWQTTYPdC&index=14
2. Calculation Groups: https://www.youtube.com/watch?v=WnLtC3udzSQ
3. Create Date Table: https://www.youtube.com/watch?v=wN1ok8JDzrI

