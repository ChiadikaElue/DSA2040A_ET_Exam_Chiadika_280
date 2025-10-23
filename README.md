# Chiadika Elue 280
# DSA 2040A - Mid Semester Exam

## Project Overview
This project demonstrates Extract and Transform operations on the Online Retail II dataset from UCI Machine Learning Repository. The dataset contains transactional data from a UK-based online retail store, including information about purchases, customers, and products.

## Data Source
- **Dataset**: Online Retail II Data Set
- **Source**: UCI Machine Learning Repository
- **Link**: https://archive.ics.uci.edu/ml/datasets/Online+Retail+II
- **Description**: This dataset contains all the transactions occurring for a UK-based and registered non-store online retail between 01/12/2009 and 09/12/2011. The company mainly sells unique all-occasion gifts.

## ET Phases

### Extract Phase
- Loaded raw dataset (~540,000 rows) and incremental subset
- Performed data profiling using `.head()`, `.info()`, and `.describe()`
- Identified and documented data quality issues:
  1. Missing values in CustomerID and Description columns
  2. Inconsistent data types (dates as strings)
  3. Negative quantities and unit prices (cancelled orders)
  4. Duplicate records
- Merged datasets by appending incremental data
- Saved validated copies for transformation

### Transform Phase
Applied 7+ transformations across multiple categories:

1. **Cleaning**: Handled missing values in CustomerID and Description
2. **Cleaning**: Removed duplicate records
3. **Structural**: Standardized data types (datetime, numeric, string)
4. **Enrichment**: Added derived columns (TotalAmount, date components)
5. **Categorization**: Created sales brackets based on transaction amount
6. **Filtering**: Removed invalid records (negative quantities/prices)
7. **Standardization**: Cleaned and standardized text data

## Tools Used
- Python 
- Pandas for data manipulation
- Jupyter Notebook for interactive development
- Git for version control

## Steps to Run the Project

1. Clone the repository:
git clone <repository-url>
cd DSA2040A_ET_Exam_Chiadika_280

Ensure required packages are installed:
pip install pandas numpy matplotlib seaborn jupyter

Run the extraction notebook:
jupyter notebook etl_extract.ipynb
Execute all cells in order

Run the transformation notebook:
jupyter notebook etl_transform.ipynb

Execute all cells in order

Check the output files in /data and /transformed directories

## Sample Output

Transformed data info:
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 5 entries, 0 to 4
Data columns (total 13 columns):
 #   Column        Non-Null Count  Dtype         
---  ------        --------------  -----         
 0   InvoiceNo     5 non-null      int64         
 1   InvoiceDate   3 non-null      datetime64[ns]
 2   Quantity      5 non-null      int64         
 3   UnitPrice     5 non-null      float64       
 4   CustomerID    5 non-null      object        
 5   Description   5 non-null      object        
 6   Country       5 non-null      object        
 7   TotalAmount   5 non-null      float64       
 8   Year          3 non-null      float64       
 9   Month         3 non-null      float64       
 10  DayOfWeek     3 non-null      object        
 11  Hour          3 non-null      float64       
 12  SalesBracket  5 non-null      object        
dtypes: datetime64[ns](1), float64(5), int64(2), object(5)

