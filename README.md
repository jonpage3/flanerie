# flanerie

A spine view online library catalog using a dataset retrieved through the Sierra ILS.

Master branch of project hosted here: https://opal.ils.unc.edu/~jepage/flanerie/. Dataset used is items from the UNC Chapel Hill collection stored at the TRLN Library Service Center. 

Previous repositories [here](https://github.com/jonpage3/library_browser) and [here](https://github.com/jonpage3/csv_data_cleaning). 

## Data Collection

Using Sierra’s Create Lists retrieve a set of items (suggested search parameters given in data/search.json) , and collect under following parameters and store in csv file using following column headers:

| Sierra Field Name   | Description |CSV column name |
| ------------------- | ----------- |----------------
| Header              | Title       |
| Paragraph           | Text        |

Store in csv file named “input.csv” in data folder.

## Data Cleaning

Requirements:
Within data folder run: 
pip install -r requirements.txt. 
From the python console:
import nltk
nltk.download(‘stopwords’)

Run main.py

## Visualization

Uses the D3 library to create a “spine view” online library catalog that supports filter, ‘start at’ browsing, and individual book view of item contents. Main parameters can be adjusted in the following files:

src/flanerie.js
css/main.css

To install using npm:
git pull origin node_branch
npm install
