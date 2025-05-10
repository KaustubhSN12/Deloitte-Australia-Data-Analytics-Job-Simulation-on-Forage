
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

## ✅ Task 2: Gender Pay Equality Analysis in Excel

### 🎯 Objective

Classify job roles based on the level of **gender pay equality** using provided scores.

---

### 🧰 Tools Required

* Microsoft Excel or Google Sheets

---

### 🔧 Step-by-Step Instructions

#### 1. **Download the Dataset**

* File: `Equality Table.xlsx` or `Equality Table.csv`
* Open it in Excel.

#### 2. **Add a New Column**

* Insert a new column: `Equality Class` in **Column D**
* In cell **D2**, paste this formula:

```excel
=IF(ABS(C2)>20, "Highly Discriminative", IF(ABS(C2)>10, "Unfair", "Fair"))
```

#### 3. **Apply Formula to All Rows**

* Drag the formula from D2 down to fill all rows.
* Ensure formatting and results look correct.

#### 4. **Validate Results**

* ✅ Score `10` → "Fair"
* ✅ Score `-9` → "Fair"
* ✅ Score `-30` → "Highly Discriminative"

#### 5. **Save Your Work**

* Save as: `Equality Table - Updated.xlsx`

---

### 💡 Tips

* **ABS()** ensures positive comparison for both negative and positive scores.
* Always double-check your logic with a few manual calculations.

---

## 📥 Resources

* Tableau Trial: [https://www.tableau.com/products/trial](https://www.tableau.com/products/trial)
* Excel Online: [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)
* Sample Equality Table: *(Attach or provide path)*
* Telemetry JSON file: *(Attach or provide path)*

---

## 📌 Submission Checklist

| Task   | Requirement                            | Done |
| ------ | -------------------------------------- | ---- |
| Task 1 | Dashboard created in Tableau           | ✅    |
| Task 1 | Screenshot taken of filtered dashboard | ✅    |
| Task 2 | Excel formula applied                  | ✅    |
| Task 2 | File saved with Equality Class column  | ✅    |

---

## 🙌 Credits & Connect

This walkthrough was created and maintained by **\[Your Name]** – a passionate data analyst and problem solver!

🔗 **Check out more projects:**

* [GitHub Portfolio](https://github.com/yourusername)
* [LinkedIn Profile](https://www.linkedin.com/in/yourusername)
* [Other Repositories](https://github.com/yourusername?tab=repositories)

🎯 If this guide helped you, consider starring ⭐ the repository and following for more walkthroughs and analytics content.

---

Let me know your preferred name, GitHub URL, and LinkedIn handle, and I’ll insert them into the final markdown file for you. Would you like me to generate a downloadable `.md` file next?
