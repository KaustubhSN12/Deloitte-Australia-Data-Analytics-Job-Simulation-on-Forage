
---

# 📊 Daikibo Analytics Job Simulation – Step-by-Step Guide

Welcome to the Deloitte-Australia-Data-Analytics-Job-Simulation-on-Forage . This guide will help you navigate and solve both tasks using **Tableau** and **Excel**, providing detailed instructions, helpful links, sample commands, and expected outcomes.

---

## ✅ Task 1: Machine Down Time Analysis in Tableau

### 🎯 Objective

Use telemetry data to visualize machine downtime and answer:

* In which **location** did machines break the most?
* What **machine types** broke most often in that location?

---

### 🔧 Step-by-Step Instructions

#### 1. **Download & Install Tableau**

* Visit [Tableau Free Trial](https://www.tableau.com/products/trial)
* Use your email to **download** and **register** Tableau.

#### 2. **Download & Import Data**

* Download the file: `daikibo-telemetry-data.json.zip` from the resources.
* Unzip it.
* Open Tableau → **Connect** → Choose `JSON` → Import `daikibo-telemetry-data.json`.

#### 3. **Create a Calculated Field**

* Go to **Data Pane** → Right-click → *Create Calculated Field*
* Name: `Unhealthy`
* Formula:

  ```plaintext
  IF [Status] = "Unhealthy" THEN 10 ELSE 0 END
  ```
* This represents **10 minutes** of downtime per "Unhealthy" status.

#### 4. **Create First Sheet: "Down Time per Factory"**

* Drag `Factory` to Columns.
* Drag `Unhealthy` to Rows.
* Set aggregation to **SUM**.
* Sort bars descending by downtime.
* Rename Sheet: `Down Time per Factory`

#### 5. **Create Second Sheet: "Down Time per Device Type"**

* Drag `Device Type` to Columns.
* Drag `Unhealthy` to Rows.
* Filter: Select a specific factory if needed.
* Rename Sheet: `Down Time per Device Type`

#### 6. **Build a Dashboard**

* Click `New Dashboard`.
* Drag both sheets onto the dashboard.
* Click the first chart → Use as Filter (right-click on chart).
* When a factory is selected, the second chart updates accordingly.

#### 7. **Capture & Submit**

* Click on the factory bar with **highest downtime**.
* Take a screenshot of your dashboard.
* Save and submit as instructed.

---

### 🧪 Example Output

| Factory  | Total Downtime (mins) |
| -------- | --------------------- |
| Meiyo    | 32,000                |
| Seiko    | 28,900                |
| Shenzhen | 22,500                |
| Berlin   | 19,200                |

**Dashboard Preview:**

> ![Example Dashboard Screenshot](https://i.imgur.com/ZkdCv0L.png) *![output-dashboard](https://github.com/user-attachments/assets/ee52e6dc-ea27-4448-b645-afa881d44f87)*

---

### ✅ Task 2: Create Equality Classification in Excel
🎯 Objective
Generate a new column Equality Class based on the values in the Equality Score column.

### 🧰 Tools Required
Microsoft Excel or Google Sheets

### 🔧 Step-by-Step Instructions
1. Open the Dataset
File: Equality Table.xlsx (or .csv)

### Open in Excel

2. Add a New Column
Column D → Header: Equality Class

In cell D2, paste:

```plaintext
=IF(ABS(C2)>20, "Highly Discriminative", IF(ABS(C2)>10, "Unfair", "Fair"))
```

3. Drag Formula Down Fill the formula through all rows

### 4. Validate a Few Rows
   
* -25 → Highly Discriminative

* -15 → Unfair

*  → Fair

### 5. Save Your File
Save as: Equality Table - Updated.xlsx

### 🧾 Example Data Preview
* Factory	Job Role	Equality Score	Equality Class
* Daikibo Meiyo	C-Level	-25	Highly Discriminative
* Daikibo Seiko	Manager	-21	Highly Discriminative
* Daikibo Shenzhen	Engineer	4	Fair

### ✅ Confirm your file looks like this before submitting.

### 📥 Resources
* Tableau Trial
* Excel Online


### 📌 Submission Checklist
* Task	Requirement	Done
* Task 1	Dashboard created in Tableau	✅
* Task 1	Screenshot taken of filtered dashboard	✅
* Task 2	Excel formula applied	✅
* Task 2	File saved with Equality Class column	✅

### 🙌 Credits & Connect
This guide was created by Kaustubh Narayankar, an aspiring data analyst dedicated to helping others break into the data field.

### 📍 Explore more:

🔗 GitHub: https://github.com/KaustubhSN12

💼 LinkedIn: [https://linkedin.com/in/yourusername](https://www.linkedin.com/in/kaustubh-narayankar-6651a9249/)

⭐ If you found this guide helpful, please star the repo and follow for more analytics walkthroughs.

