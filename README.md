# Project 2: Crowdfunding_ETL

Group 4: Alvin, Kristina, Mason, Lisa and Frank

## Introduction

For the ETL mini project, we will work in a group of 5 to practise building an ETL pipeline using Python, Pandas, and either Python dictionary methods or regular expressions to extract and transform the data. After transforming the data, we create four CSV files and use the CSV file data to create an ERD and a table schema. Finally, we upload the CSV file data into a Postgres database.

## Programming Technique

We have been used Pair Programming, in this case, group programming where 5 of us work together at one workstation. On team member, called the "driver", writes and execute the code while the others, known as the "observers" or "navigators," reviews each line of code as it is written, give feedback or recommendations as well as advice on debugging. We have switched roles frequently among us in order to balance the coding time between all members.

This collaborative approach has several benefits:

  1. Improved Code Quality: The constant review process helps catch mistakes early, leading to higher quality code.
  2. Knowledge Sharing: It facilitates the sharing of knowledge between team members, helping less experienced programmers learn from their more experienced counterparts.
  3. Enhanced Problem-Solving: More people working on the same problem can come up with more creative and effective solutions than one person working alone.
  4. Increased Team Communication: It improves communication within the team, leading to better teamwork and collaboration.
  5. Reduced Risk of Burnout: Switching roles regularly helps keep all programmers engaged and reduces the risk of burnout.

## Data Transformation 

### Create Category and Subcategory DataFrames

#### Category DataFrame:

Extract and transform crowdfunding.xlsx data.

Columns: category_id (sequential from cat1 to catn), category (category titles).

Export as category.csv and save to GitHub.
  
#### Subcategory DataFrame:

Extract and transform crowdfunding.xlsx data.

Columns: subcategory_id (sequential from subcat1 to subcatn), subcategory (subcategory titles).

Export as subcategory.csv and save to GitHub.
  
#### Create Campaign DataFrame

Extract and transform crowdfunding.xlsx data.

Columns:
    cf_id, contact_id, company_name, description (renamed from blurb), goal (float), pledged (float), outcome, backers_count, country, 
    currency, launch_date (renamed from launched_at and converted to datetime format), 
    end_date (renamed from deadline and converted to datetime format), category_id, subcategory_id.
    
Export as campaign.csv and save to GitHub.
  
#### Create Contacts DataFrame

Import contacts.xlsx into a DataFrame.

Convert each row to a dictionary.

Extract dictionary values and add them to a new list.

Create a new DataFrame from this list.

Split name column into first_name and last_name.

### Database Creation

#### Create the Crowdfunding Database
Inspect the four CSV files.

Sketch an ERD using QuickDBD.

Create a table schema for each CSV file (specifying data types, primary keys, foreign keys, and other constraints).

Save the schema as crowdfunding_db_schema.sql and save to GitHub.

Create a new Postgres database named crowdfunding_db.

Use the schema to create the tables in the correct order.

Verify table creation with a SELECT statement for each table.

Import each CSV file into its corresponding SQL table.

Verify the data with a SELECT statement for each table.
