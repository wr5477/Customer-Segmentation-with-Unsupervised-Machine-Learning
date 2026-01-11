# Customer Segmentation Analysis (Unsupervised ML)
End-to-end customer segmentation project using Python and unsupervised machine learning to derive actionable marketing insights from retail customer data.

## Overview (End-to-End Workflow)
Most companies collect customer and purchase data, but running broad, untargeted campaigns can waste budget.  
This project builds **data-driven customer segments** to help a retail business tailor promotions and product strategies to the right audiences.

**Cleaning → Feature Engineering → Preprocessing (Encoding & Scaling) → PCA → Clustering → Insights & Marketing Strategy (Slides)**

<p align="center">
 <img width="449" height="459" alt="image" src="https://github.com/user-attachments/assets/49ed5c1c-47c5-48b9-b6f8-ad1634b08fcf" />
</p>
**Goal:** Identify meaningful customer clusters and translate them into practical marketing actions.

---

## Workflow (What I Did)

### 1) Data Loading & Initial Audit
- Loaded the retail marketing campaign dataset into a Pandas DataFrame.
- Inspected shape, column types, and missing values (e.g., missing `Income`).

<img width="1539" height="265" alt="image" src="https://github.com/user-attachments/assets/2162fda5-2da8-405d-a2a7-c381fdc288c7" />
<img width="407" height="434" alt="image" src="https://github.com/user-attachments/assets/90f2ae39-e330-4eaa-bb76-8cb140b6d64c" />

---

### 2) Data Cleaning (Missing Values + Outliers)
- Removed rows with missing values (especially in `Income`) to ensure clean input for ML.
- Identified unrealistic outliers in key numeric fields (e.g., extremely high age/income).
- Applied caps to remove extreme outliers before modeling (example: Age > 90, Income > 600,000).

<img width="1328" height="1228" alt="image" src="https://github.com/user-attachments/assets/16ddf7f6-9f42-4f08-a111-a27c48e9a80d" />

---

### 3) Feature Engineering (Making Data More ML-Ready)
Created additional features to better represent customer behavior and household structure:
- **Age** from year of birth
- **Customer tenure** (how long the customer has been enrolled) from `Dt_Customer`
- **Total spend** across product categories
- **Living_With** (Partner vs Alone) from marital status
- **Children**, **Family_Size**, and **Is_Parent** based on household information
- Simplified education levels into broader categories

---

### 4) Preprocessing for Machine Learning (Encoding + Scaling)
- Converted categorical variables into numeric form using **Label Encoding** (e.g., Education, Living_With).
- Applied **feature scaling (StandardScaler)** to ensure fair feature weighting in distance-based learning.

  <img src="https://github.com/user-attachments/assets/9f16511e-981f-4f46-8653-543a6f59326d" width="700" alt="Encoding & Scaling preview" />

---

### 5) Dimensionality Reduction with PCA
Because many features are correlated/redundant, I used **PCA (Principal Component Analysis)** to compress information:
- Reduced the dataset to **3 principal components**
- Enabled easier clustering + 3D visualization of customers

<p align="center">
  <img src="https://github.com/user-attachments/assets/367c7428-ad4d-44eb-8368-dfe297980453" width="520" alt="3D PCA projection" />
</p>

---

### 6) Clustering (Finding Customer Segments)
- Determined the optimal number of clusters using the **Elbow Method**
- Selected **K = 4**
- Built clusters using **Agglomerative (Hierarchical) Clustering**

<p align="center">
  <img src="https://github.com/user-attachments/assets/50f7c140-8b08-466a-b113-6f95638694ec" width="650" alt="Elbow method (k=4)" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/7caf007d-8cef-4bbb-96f7-0463c054218a" width="520" alt="3D clusters visualization" />
</p>

---

### 7) Cluster Interpretation & Insights
After clustering, I profiled each group using behavior and demographic patterns:
- Spending vs income differences
- Household composition (parent vs non-parent, family size, teens at home)
- Promotion and deal sensitivity

<p align="center">
  <img src="https://github.com/user-attachments/assets/f653983a-e446-4afd-a06d-b7b1aae358a0" width="420" alt="Spend vs income by cluster" />
  <img src="https://github.com/user-attachments/assets/1e200f2f-628d-4708-9625-cadddb21b566" width="420" alt="Spend distribution by cluster" />
</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/6a4b79ec-ef9b-40c6-8b91-3398501599d9" width="520" alt="Deals / promotions insight by cluster" />
</p>


---

## Cluster Profiles & Marketing Recommendations

### Cluster 0 — Deal-Driven Family Shoppers
- Parents in 2–4 person households; many have teenagers; relatively older
- Strong discount/deal responsiveness  
**Strategy:** value packs, multi-buy deals, family bundles, and a mix of traditional + digital marketing.

### Cluster 1 — Young Families with Low Spending
- Younger parents with smaller households, typically one young child
- Lower overall spending  
**Strategy:** child-focused convenience promotions, app-based coupons, fresh/organic/baby-related products.

### Cluster 2 — High-Income, Non-Parent Segment
- Mostly couples/individuals (1–2 household size), high income, low discount sensitivity  
**Strategy:** premium and specialty products, curated bundles, experience-focused marketing (not discount-driven).

### Cluster 3 — High-Spending Parents with Budget Constraints
- Larger families often with teenagers; lower income but high spending needs  
**Strategy:** private-label products, bulk discounts, strong loyalty programs, heavy promotion of weekly deals.

---

## Deliverables
- **Jupyter Notebook:** full end-to-end workflow (cleaning → features → PCA → clustering → insights)
- **Cluster Strategy Summary PDF:** customer profiles + recommended marketing actions
- **Presentation Deck (PDF):** a quick, high-level summary deck created using **Gamma** for fast communication of the project story in a professional format.

<img width="923" height="518" alt="image" src="https://github.com/user-attachments/assets/82ced695-6c72-4abd-92ab-63c9b48dc79b" />

---

## Reference
- YouTube: **Lore So What**
