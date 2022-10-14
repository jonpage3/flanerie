# flanerie

A spine view online library catalog using a dataset retrieved through the Sierra ILS.

Master branch of project hosted here: https://opal.ils.unc.edu/~jepage/flanerie/. Dataset used is items from the UNC Chapel Hill collection stored at the TRLN Library Service Center. 

Previous repositories [here](https://github.com/jonpage3/library_browser) and [here](https://github.com/jonpage3/csv_data_cleaning). 

## Data Collection

Using Sierra’s Create Lists retrieve a set of items (suggested search parameters given in data/search.json) , and collect under following parameters and store in csv file using following column headers:

| Sierra Field Name   | Description |CSV column name |
| ------------------- | ----------- |----------------
| Call No.              | LCCN call number.       |callnum|
| Volume           | Volume of item if in a set.      |vol|
|Total Checkouts|Number of times item has been checked out.|checkouts|
|MARC Tag 245a|Title of the work.|title|
|MARC Tag 245b|Remainder of title.|title2|
|MARC Tag 100|Author’s name.|author|

Store in csv file named “input.csv” in data folder.

## Data Cleaning

#### Requirements:

Within data folder:<br>
pip install -r requirements.txt. 

From the python console:<br>
import nltk<br>
nltk.download(‘stopwords’)<br>

python main.py

## Visualization

Uses the D3 library to create a “spine view” online library catalog that supports filter, ‘start at’ browsing, and individual book view of item contents. 

Main parameters can be adjusted in the following files:<br>
src/flanerie.js<br>
css/main.css

To install using npm:<br>
git pull origin node_branch<br>
npm install
