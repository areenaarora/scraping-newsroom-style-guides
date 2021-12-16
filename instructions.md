### Instructions ###
To run this project locally on your computer, you'll need: Python, Jupyter Notebook and Excel installed.
Within Python, you will also need the Pandas library.

To install Python: Follow the instructions [here](http://littlecolumns.com/tools/python-wrangler)
To install Jupyter Notebook: Follow the instructions [here](https://jupyterlab.readthedocs.io/en/stable/getting_started/installation.html)
To install Pandas: Follow the instructions [here](https://pandas.pydata.org/docs/getting_started/install.html)
*For Reuters, I used PDF miner to extract text from the PDF and converted it into an HTML file. To run the Reuters notebook, you can skip the PDF part and just download the HTML file [here](reuters/reuters-styleguide.html)*

Each newsroom folder has the individual notebooks I used to scrape each website. If you'd like to just see the final product, skip those and head to the [all-combined](all-combined) folder. Download the cleaned excels from here and the [all-combined](all-combined/all-combined.ipynb) notebook to run locally.

If you'd like to skip all this and just browse through the database I've created, here are the links to each individual style guides (cleaned up for formatting, but not edited): To download, click on 'View raw'
- [BBC](all-combined/bbc_cleaned.xlsx)
- [BuzzFeed](all-combined/buzzfeed_cleaned.xlsx)
- [NPR](all-combined/npr_cleaned.xlsx)
- [Reuters](all-combined/reuters_cleaned.xlsx) 
- [Guardian](all-combined/guardian_cleaned.xlsx)

*(Please note, these excels were scraped and cleaned between Dec 7-15, 2021 and do not have updates thereafter. For updated data, please run the entire codebase)*