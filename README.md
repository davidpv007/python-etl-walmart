**Walmart Sales ETL Pipeline**
End-to-end ETL pipeline that cleans, transforms, and loads retail sales data into PostgreSQL using polars and pandas.

**main issue with the original dataset**

Raw Walmart sales data contained duplicates, nulls, and inconsistent pricing formats that prevent reliable analysis in PostgresSQL

**Solution overview (ETL flow)**

- Extract CSV data using kaggle API
- Transform with Polars (cleaning, casting, deduplication)
- Load into PostgreSQL
  
**Tech stack**
-Python 
-Polars
-Pandas
-PostgreSQL
-PyArrow
-Git
-Jupyter

**Data cleaning & transformations**

- Full-row deduplication using **`pl.struct(pl.all())`**
- Null and NaN removal
- String sanitization (`$`, whitespace)
- Numeric type casting
- Derived metrics (total sales)

The pipeline removes full-row duplicates using **pl.struct(pl.all())**, normalizes price formats, casts numeric columns, and computes total sales.

**Database schema / destination**

Created a db in PostgresSQL for making the data ready for analysis.

**Run the project**

pip install -r requirements.txt
python scripts/etl_walmart.py

**Project structure** 

Data_projects/
│── notebooks/        # Exploratory analysis and data cleaning
│── scripts/          # Production-ready ETL scripts
│── README.md         # Project documentation
│── requirements.txt  # Python dependencies








