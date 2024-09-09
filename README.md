# Crowdfunding ETL Process

## Project Overview

The project aims to extract, transform, and load (ETL) data from a crowdfunding campaign dataset and contacts dataset. The project demonstrates how to clean and organize data, split category and subcategory fields, generate unique identifiers, and merge datasets for further analysis.

## Technologies Used

* Python 3.x
* Pandas
* Numpy
* JSON
* Excel (for `.xlsx` file reading)
* CSV (for exporting cleaned data)


## Data Extraction

We begin by extracting data from:

  * `crowdfunding.xlsx`: Contains information about various crowdfunding campaigns such as the project goal, amount     pledged, backers, and category/subcategory.
  * `contacts.xlsx`: Contains contact information of individuals associated with each campaign.

The data is loaded into Pandas DataFrames for manipulation and analysis.

## Data Transformation 

### Crownfunding Data

1. Category & Subcategory Extraction:

  * The `category & sub-category` column is split into separate `category` and `subcategory` columns.
  * Unique `category_id` and `subcategory_id` are created for each unique category and subcategory.

2. Campaign DataFrame:

  * Renamed relevant columns (`blurb` to `description`, `launched_at` to `launch_date`, `deadline` to `end_date`).
  * Converted `goal` and `pledged` columns from integers to floats.
  * Formatted `launched_date` and `end_date` columns to datetime format.
  * Merged campaign data with category and subcategory data based on the `category` and `subcategory` columns.

3. Contacts Data:

  * The contact data from `contacts.xlsx` was converted from JSON format to a structured DataFrame.
  * First and last names were extracted from the full name, and an additional `email` column was retained.

### Exported Data

1. **Categories**: Exported the `category` DataFrame to `category.csv`.
2. **Subcategories**: Exported the `subcategory` DataFrame to `subcategory.csv`.
3. **Campaigns**: Exported the cleaned `campaign` DataFrame to `campaign.csv`.
4. **Contacts**: Exported the cleaned `contacts` DataFrame to `contacts.csv`.

## Data Loading

All transformed datasets were exported as CSV files for easy accessibility and further analysis.

## Database Creating

* Inspect the four CSV files.
* Sketch an ERD using QuickDBD.
* Create a table schema for each CSV file (specifying data types, primary keys, foreign keys, and other constraints).
* Save the schema as crowdfunding_db_schema.sql and save to GitHub.
* Create a new Postgres database named crowdfunding_db.
* Use the schema to create the tables in the correct order.
* Verify table creation with a SELECT statement for each table.
* Import each CSV file into its corresponding SQL table.
* Verify the data with a SELECT statement for each table.

## Repository Structure

* **Resources**: Contains all data files.
* **ETL**: Contains main lines of code.
* **README.md**: Overview of the repository.
* **LICENSE**: License of the repository

## How to Use

1. Clone the repository:

```python
git clone https://github.com/alvin-giang/Crowdfunding_ETL.git
cd Crowdfunding_ETL
```

2. Install dependencies:

You can install the necessary Python libraries by using the following command:

```python
pip install pandas numpy
```

3. Run the Jupyter Notebook:

Use Jupyter to open and run the notebook `Crowdfunding_ETL.ipynb` for step-by-step data extraction, transformation, and loading.

4. Review CSV outputs:

Check the `Resources` folder for the cleaned and exported data files in CSV format.

## License

This project is licensed under the **MIT License**.


