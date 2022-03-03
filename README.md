# Comparing news agencies' style guides

## UPDATE:
I scraped the styleguides again on February 26, 2022 and you can find a searchable version here:
[Searchable styleguides database](https://areenaarora.com/comparing-newsrooms-styleguides/)

## Goal

Compare how different words are defined by different news organizations to get an insight into their editorial decisions.

My hope is comparing older news orgs like Reuters to newer ones like BuzzFeed will be reflective of the industry's editorial direction as a whole. The news orgs I've chosen have a wide ranging readership and would be interesting to measure all these five on the same scale. Some editorial decisions taken in this analysis include not scraping some unique features of each style guide — just in the interest of maintaining standardization across the board.

## What will the final tech product(?) look like?

User inputs a word and gets five different definitions (from Reuters, NPR, Buzzfeed, BBC, The Guardian).

## Tech stack used:
- Python — BeautifulSoup and Pandas
- Regex
- PDFMiner
- HTML
- Excel

## Instructions
Please check out [instructions](instructions.md)

## Process summary

1. Choose style guides to scrape

   I picked [Reuters](https://www.reuters.com), [BBC](https://www.bbc.com), [The Guardian](https://www.theguardian.com/international), [NPR](https://www.npr.org/sections/news/) and [BuzzFeed](https://www.buzzfeednews.com). I wanted to include AP and a couple local news orgs as well, but in the interest of keeping the scope of the project manageable with the given time frame, chose to stick to these five. Some (like AP's) just weren't available for free!

2. Used Beautiful Soup to scrape. Used Regex to analyze text.

### Style guide formats:

- BBC: [A-Z guide on one page plus additional pages for numbers, punctuation, military, religious names](https://www.bbc.co.uk/newsstyleguide/)
- The Guardian: [26 pages one for each alphabet](https://www.theguardian.com/guardian-observer-style-guide)
- NPR: [Single web page](https://training.npr.org/styleguide/)
- BuzzFeed: [Single web page](https://www.buzzfeed.com/emmyf/buzzfeed-style-guide)
- Reuters: [PDF](https://www.trust.org/contentAsset/raw-data/652966ab-c90b-4252-b4a5-db8ed1d438ce/file)

## Process

1. Scrape BuzzFeed
2. Scrape NPR
3. Scrape BBC
4. Scrape the first page of The Guardian
5. Figure out how to automate through different pages for The Guardian -- used a list of alphabets to iterate through all the links
6. Put all these four in a list of dictionaries format
7. Save these lists of dictionaries into data frames
8. Scrape Reuters' PDF using Tika
9. Put Reuters' style guide into a list of dictionary format
10. Create a dataframe for Reuters
11. Convert individual dataframes into excels
12. Clean each excel
13. Convert the clean excels back to dataframes
14. Write code to input word (case insensitive!!!) and search through each dataframe ---> Figure out how to standardize with British and American spellings
15. Produce output
16. Test out a couple of words and write about the analysis

## Summaries scraping each style guide
BuzzFeed, NPR, BBC and Guardian all scraped with BeautifulSoup

### BuzzFeed
The entire style guide is on one page. It's not very long and extensive (good for coding, bad for human-world analysis)
All entries wrapped in `<p>` tags!

Some `<p>` tags contained multiple entries!! So figuring out how to split those was challenging.

### NPR
Fairly consistent with all of it being on one page and all the words nested inside <p> tags

### The Guardian
Robust data set and even though it was split over multiple pages, I was able to scale the same code without many issues

### BBC
Separated words and guidelines by their strong tags.

### Reuters
Downloaded specific pages of the PDF that I needed to scrape from. Read PDF using PDFminer and then converted it into html. Used BeautifulSoup then.


## Post scraping

I'd originally thought of creating one big dataframe which would have six columns — one for the words, and five for style rules from each source. I later decided to keep dataframes separate for two reasons: One: Words are very inconsistent with each other. For instance, NPR's guide has about 500 entries compared to over 4,500 for The Guardian. And, secondly because it would've involved a lot of complicated regex (accounting for special characters, accents and British and American spellings)

So, after creating individual dataframes, I exported them into individual excels to clean them up. The biggest cleaning challenge was with Guardian — some words had multi-paragraph guides which didn't get scraped with 100% accuracy. Luckily though, the excel rows were not thrown off by it.

The first function I wrote was searching for exact matches in the word columns of each dataframe, but I realized that one it was missing out on words that were in a different case from the user's input and inputting absolute exact matches isn't always going to be the case. For instance: The input 'terror' captures: terrorism, terrorist, war on terror etc

### Interesting cases/suggested searches:
- Americanisms
- assisted suicide
- bomb warning / hoax
- -ization, -isation
- military terminology
- families
- gategate
- gender issues
- Geneva conventions
- Sheikh
- Roman numerals
- told
- cash me ousside, howbow dah
- And my favorite 🥁🥁🥁 CHICKEN TIKKA MASALA!