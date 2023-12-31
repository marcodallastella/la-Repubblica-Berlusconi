# laRepubblica Berlusconi
 
This repository include the notebooks used to scrape and analyze more than 31,000 headlines published by the Italian newspaper [laRepubblica](https://www.larepubblica.it) about Silvio Berlusconi.

## Summary of findings
Over the course of the years laRepubblica published 31,805 articles with headlines containing the words 'berlusconi' or 'silvio'.
These articles spiked in 2013, when Berlusconi was sentenced for tax evasion. In that year, laRepubblica published 3,130 articles about the former Italian Prime Minister.

Among the words most commonly associated with Berlusconi in headlines, some interesting trends emerge.

The person most frequently mentioned is the leader of the right-wing party North League, Matteo Salvini, with 726 occurrences, followed by the former progressive leader Matteo Renzi, with 622.

The most-common verb is "attack" (436 headlines), while 297 headlines involve the word "trial" and 230 the word "crisis". The word "decadence" appeared in 149 headlines.

## Notebooks

1. laRepubblica scraper
2. Word analysis


## Data collection

### 1. Scraper

This notebook uses the search function of laRepubblica's website to search for the word 'berlusconi' and retrieve any headline containing the word 'berlusconi' or 'silvio'.

Because search results are limited to 50 pages, after the 50th page the page number goes back to 1 and the `date` variable is updated with the date of the most recent article. This will create duplicates that needs to be removed before saving the csv file.

Output: `headlines.csv`


### 2 Word analysis

This notebook does some basic cleaning (such as adding a `Year` column to our df) before using `nltk` for the tokenization of headlines. It then selects the top-30 most recurring words for each year and save them in an external file.

The same file is then used locally to assign to each word a corresponding category and reloaded to the notebook for some basic analysis and visualizations.

Outpouts: `result_df.csv`, `unique_words.csv` and one `category.csv` for each assigned category.

## Tools, skills, approaches

* I used `for loops` to scrape more than 31,000 headlines from the website of laRepubblica.
* I used [NLTK](https://www.nltk.org/) for the tokenization of headlines.

## Missed opportunities

* Other websites and newspapers could be scraped as well.
* Some NLP tools are not as reliable in Italian as they are in English. For example, I didn't do any sentiment analysis.
* Word categorization is a lenghty and boring process which limits the ability to process the data in a reasonable time.

Marco Dalla Stella

[md3934@columbia.edu](mailto:md3934@columbia.edu)