# Power BI Adventure Works Analysis

**[Power BI] Adventure Works Analysis**

**I. Introduction**
The Production Department at AdventureWorks manages the manufacturing process, starting from receiving raw materials to producing and storing finished goods across multiple locations for distribution. Production timelines may not always match plans, and quality checks are conducted to remove defective items, ensuring only high-quality products are stored and sold. An **Operation Dashboard** will offer the Production Director a clear, visual overview of key metrics and processes, enabling more informed decision-making and streamlined operations.

**Dataset**

Dataset: adventureworks2019 (public Google BigQuery dataset)

Dataset dictionary:  AdventureWorks _ Data Dictionary

Dataset access:

- Log in to your Google Cloud Platform account and create a new project.
- Navigate to the BigQuery console and select your newly created project.
- In the navigation panel, select "Add Data" and then "Star a project by name".

**II. Design Thinking Steps**

**Step 1 - Empathize**
| 5W1H                                                          |                                           |
| ------------------------------------------------------------------ |--------------------------------------------- |
| Who will be viewing this Dashboard?                                | Product manager<br> |
| If we had to choose only one key Stakeholder, who would it be?<br> | Product manager |
| What problem does this Dashboard solve?                            | Observe whetther production time is in accordance with the planned time<br>Minimize scrapped products.<br> |
| Describe the problem in one sentence                               | Manufacturing needs to track the quantity of scrapped products and the delivery time of products to ensure there are enough goods for distribution as well as to minimize the costs associated with scrapped products<br> |
| When and where will Stakeholders view this Dashboard?<br>          | Weekly, monthly<br> |
| Why do stakeholders need this Dashboard?<br><br>                   | Ensure that the company always has enough products to supply to customers<br>Improve the production process to minimize costs related to scrapped goods|
| How have stakeholders been achieving their goals so far?           | Improve the production process<br>Apply modern technology and machinery |


|Stakeholder Empathy Mapping                                                         |                                                          |
| ---------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Pains                                                      | Find out the cause of scrapped products and delays.                                                      |
| Thinking and feeling                                       |The production process needs to be improved         |
| Seeing                                                    | Production process is inefficient.                                        |
| Saying and doing                                          | Track production progress for each product, at each location<br>Track the amount of scrapped goods over time for each item, try to find out the reason behinds |
| Gains                                                     | Improving production processes will likely increase profits through increased sales and reduced production costs                            |


| Fact table<br>                        | Dim table<br>                                                 |
| -------------------------------------- | -------------------------------------------------------------- |
| Production_WorkOrder, Product_Product | Dim_date, Product_Inventory, Product_ProductTable, Production_BillofMaterials, Production_Location, Production_ScrapReason, Production_WorkOrderRouting |

### Step 2 - Define POV

|                            | NORTHSTAR METRIC                         |
|----------------------------|--------------------------------------|
| **What VALUE you want to measure?** | Delivery Success Rate                              |
| **WHEN the value DELIVERY SUCCESS?** |When orders are delivered on time, in full quantity, and meet quality standards. |
| **Northstar Metric Name**  | Delivery Success Rate                              |
| **WHY do you choose this metric?** | This is a composite indicator reflecting the overall efficiency of all three aspects: production (Completion Rate), inventory (Safety Stock Level Rate), and quality (Pass Rate). "Delivery Success Rate" measures the ability to deliver on time, in sufficient quantity, and with assured quality, which is the ultimate goal for all production and supply chain activities. |


Dimension Group
| Group 1 | Group 2  | Group 3 |
| ------- | -------- | ------- |
| Overview | Inventory analysis | Manufacturing Quality analysis |

Define Point of View
| View                     | Description                                                                                       | Why                                                                                                                     |
|--------------------------|---------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| View 1         | To provide a high-level summary of production performance, order completion, and key metrics. | Allow senior management and stakeholders to quickly grasp an overall picture of operations, including total orders, on-time completion rate, and actual costs. It helps in making strategic decisions without delving into detailed data.    |
| View 2 | To analyze and monitor inventory levels, safety stock compliance, and product availability.     | Focus on ensuring inventory is maintained at a safe level, avoiding shortages or overstock situations. It supports supply chain and warehouse management teams in optimizing inventory to meet demand without causing waste. |
| View 3 | To evaluate production quality, defect rates, and reasons for scrapped products.    | Design for the quality management team to analyze issues related to defective products, pass rates, and root causes of scrapped items. It helps improve production processes and ensures product quality meets required standards. |
### Step 3 - Ideate
Brainstorming
| Idea Name               | Layer 0 Dimension: Total Metrics              | Layer 1 Dimension: Breakdown by 1 Dimension                                   | Layer 2 Dimension: Breakdown by 2 Dimensions                                           |
|-------------------------|-----------------------------------------------|--------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| View 1       | Total Orders, Total Produced, Total Actual Cost | Total Produced by Year, Quarter and Month, Completion Rate, Total Orders by Subcategory, Product Performance |Total Produced by Year, Quarter and Month          |
| View 2| Total Inventory, Safety Stocked Products, Unsafe Stocked Products                  | Available Quantity by  Date, Proportion Comparison, Safety Status by Product Name, Available Quantity by Category |                  |
| View 3| Total Scrapped Quantity, Avg Production Time (days), Defect Rate(%)                | Quality Status by Order Quality, Scrap Trend by Date, Available Quantity and Scrapped Quantity by Product Name, Total Scrapped Quantity by ScrapReason | Available Quantity and Scrapped Quantity by Product Name                |
## III. Dashboard
### Data modeling
![Alt text](https://imgur.com/a/L6pDw93)

### View 1: Customer Segmentation Overview  
![image](https://imgur.com/a/L6pDw93)

### View 2: Monthly Segment Analysis
![image](https://github.com/user-attachments/assets/49b999af-f0ee-4139-99f9-09bc76f4d99d)

## IV. Insights
### Geographic Distribution:
