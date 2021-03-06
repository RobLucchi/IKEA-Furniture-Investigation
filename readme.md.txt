<p>
  <a href="https://www.oecd.org/pisa/">  
    
  ![IKEA](/imgs/ikea-logo-new-hero-1.jpg)
  
  </a>
</p>

# Investigating IKEA's Saudi Arabian Furniture Dataset
### By Ahmed Alaa Mousa


* [Dataset](#dataset)
* [Summary of Findings](#summary-of-findings)
* [Model Predictions](#model-predictions)

## Dataset

### Context:
This dataset is a practice of web scraping techniques. The web scraping has been applied on IKEA Saudi Arabian website for the furniture category. The scraped website link: https://www.ikea.com/sa/en/cat/furniture-fu001/

The data requested by 4/20/2020. <br>
dataset: https://www.kaggle.com/ahmedkallam/ikea-sa-furniture-web-scraping

### Content:

* item_id : item id wich can be used later to merge with other IKEA dataframes
* name: the commercial name of items
* category:the furniture category that the item belongs to (Sofas, beds, chairs, Trolleys,…)
* Price: the current price in Saudi Riyals as it is shown in the website by 4/20/2020
* old_price: the price of item in Saudi Riyals before discount
* Short_description: a brief description of the item
* full_Description: a very detailed description of the item. Because it is long, it is dropped from the final dataframe, but it   is available in the code in case it needs to be analyzed.
* designer: The name of the designer who designed the item. this is extracted from the full_description column.
* size: the dimensions of the item including a lot of details.As a lot of dimensions mentioned and they vary from item to item,
  the most common dimensions have been extracted which are: Height, Wideh, and Depth. This column is dropped from the final       dataframe, but it is available in the code in case it is needed.
* width: Width of the item in Centimeter
* height: Height of the item in Centimeter
* depth: Depth of the item in Centimeter
* sellable_Online: if the item is available for online purchasing or in-stores only (Boolean)
* other_colors: if other colors are available for the item, or just one color as displayed in the website (Boolean)
* link: the web link of the item

### Licences:
The scraped website link: https://www.ikea.com/sa/en/cat/furniture-fu001/

### Methods Used
* Data Wrangling
* Exploratory Data Analysis
* Feature engineering
* Data Visualization
  - Univariate Exploration
  - Bivariate Exploration
  - Multivariate Exploration
* etc.

### Technologies
* Python
* Pandas, , Numpy
* Matplotlib, Seaborn, plotnine
* jupyter
* sklearn, tenserflow, keras
* etc. 

<hr>

## Summary of Findings

### Data Wrangling

* hug amount of null values in the depth height and width features
* old_price feature needs some modifications:
	1. remove the "SR " string
	2. Change the "No old price" to the same price as now
	3. make it float

### Exploratory Data Analysis

* most items are sellable online (99.2%)
* and only 40% of items have other colors
* most of the items don't have any discount on it
* for low prices there is two line relations, one that shares the same line with the high prices and one limited only for low prices
* this relation is roughly 25% discount
* items from 8k to 10k SR don't have any discount that follows this relation. (only 200 SR discount)
* items that are sellable online are more expensive than those are local only

<hr>

## Model Predictions (under development)

* made two models
1. Model 1: Item's price prediction
2. Model 2: Category classifier
