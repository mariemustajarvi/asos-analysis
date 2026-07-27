# ASOS stockout & revenue analysis
<br>This Python project analyzes product data from ASOS to identify brands that may be losing revenue due to products being out of stock.<br>

<br>**Overview**

Using Python and data analysis techniques, the project estimates potential lost revenue ("phantom revenue") by combining product prices with stock availability information. The results are then visualized to highlight brands that have both premium pricing and high stockout rates.<br>
<br>
### Dataset

The analysis uses an ASOS product dataset (found in Kaggle) containing information such as:

* Product name
* Description
* Brand (extracted from product description)
* Price
* Available sizes
* Stock availability

### Technologies

* Python
* Pandas
* Matplotlib
* Seaborn<br>

### Project workflow

 **1. Data cleaning steps**

* Loaded CSV dataset
* Removed invalid price values
* Converted prices to numeric format
* Filtered missing data
  
**2. Brand extraction**

Brand names are extracted from product descriptions using string parsing.

Some inconsistent brand names are standardized, for example:

| Raw Value      | Standardized   |
| -------------- | -------------- |
| New            | New Look       |
| River          | River Island   |
| Miss           | Miss Selfridge |

Brands with fewer than five products are removed to improve analysis quality.

**3. Stockout analysis**

Each product's size information is analyzed to calculate:

* Number of out-of-stock sizes
* Stockout rate
* Estimated lost revenue

The stockout rate is calculated as:

```text
Stockout Rate = Out-of-stock sizes / Total available sizes
```

Estimated lost revenue is approximated as:

```text
Lost Revenue = Product Price × Number of Out-of-stock Sizes
```

This provides a simple indicator of products that may be losing sales because multiple size variants are unavailable.

**4. Brand-level analysis**

The data is aggregated by brand to calculate:

* Average product price
* Average stockout rate
* Total estimated lost revenue
* Number of products

Brands with fewer than 10 products are excluded from the final visualization.

**5. Visualization**

A scatter plot is used to compare brands based on:

* **X-axis:** Average Price
* **Y-axis:** Average Stockout Rate
* **Bubble Size:** Estimated Lost Revenue

Reference lines highlight brands with:

* Average price above **€40**
* Stockout rate above **40%**

These brands represent potential opportunities for inventory optimization.
<br>
<img width="1034" height="719" alt="scatterplot" src="https://github.com/user-attachments/assets/e93166ec-fd59-4617-a8e3-e9d854f1ebe6" />
*Scatterplot*
<br>
<br>
## Example Business insight

Brands with high prices and frequent stockouts may be sacrificing significant revenue because customers cannot purchase their preferred size.

This type of analysis can help retailers:

* Improve inventory planning
* Prioritize restocking
* Identify high-value products with supply issues
* Reduce missed sales opportunities
<br>

**Data analysis portfolio project demonstrating:**

* Data cleaning
* Feature engineering
* Exploratory data analysis (EDA)
* Business-oriented analytics
* Data visualization using Python
