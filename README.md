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
|MARC Tag 260a|Place of publication.|pub_location|
|MARC Tag 260b|Name of publisher.|publisher|
|MARC Tag 260c|Date of publication.|date|
|MARC Tag 300a|Number of physical pages.|length|
|MARC Tag 300c|Dimensions.|height|
|MARC Tag 505|Titles of separate works or parts of an item or the table of contents. |contents|
|MARC Tag 650|Subject headings.|subjects |
|MARC Tag 651|Geographical subject heading.|subjects2|

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

flanerie.js uses the [D3 library](https://github.com/d3/d3) to create a “spine view” online library catalog that supports filter, ‘start at’ browsing, and individual book view of item contents. 

Main parameters can be adjusted in the following files:<br>
src/flanerie.js<br>
css/main.css

To install using npm:<br>
git pull origin node_branch<br>
npm install
