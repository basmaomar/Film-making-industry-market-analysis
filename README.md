# Film-making-industry-market-analysis

## Problem Statment
Nowadays, the movie industry is one of the largest entertainment industries. It has been estimated that there are 500000 movies produced up to this point. Lately, Saudi Arabia is moving toward investing on entertainment. Therefore, giving the possibility that soon there will be a Saudi Production Film. In order to move on the right path of creating a blockbuster movie we will analyze what features contribute to a movie being successful. Beside popularity and revenue, the Oscar is the main measure of a movie’s success. Therefore, it is the highest honor in film making. We will collect IMDB data to create a dataset that will help us achieve our goal.

## Data
we collected our data using three sources:

- Scrapping IMDB website.
- OMDB API
- IMDB API
- IMDBPY library
- Obtaining a list of previous Oscar winners 
Using the previous tools, we created a dataset of more than 10,000 movies produced between 2000 and 2017. For each year we took the top 250 movies in terms of popularity, then we collected randomly 4% of the remaining movies to assure diversity in all respects.

## Cleaning
-	Margining the datasets from different sources to reduce the number of null values 
-	Remove unwanted columns, since the data produced over 40 columns which required us to drop unnecessary features that were not contributing to the prediction, such as: (Plot,	Type,	Released,	Location,	etc..)
- Fixing some values format:
  - Year (Making it into a Date-Time Format)
  - Genre (Splitting the Genres into multiple columns to reduce redundancy)
  - Finances -Budget, Gross, Cumulative, Opening- (Removing symbols, calculating currency
  - Rating (Mapping the rating to the required rating system)
  - Cast (removing the html tags and fixing the format)
  - Language (Making a Boolean column to represent English and a column to represent other languages
  - Country (Making a Boolean column to represent USA and a column to represent other countries)
- Dealing with missing values:
  - Using different data sources to fill missing values.
  - Production company: Add missing value as 'other'
  - Cast, director, writer .. etc: Since we will replace the names with weight value, we give weight 0 to unknown people.
  - Budget : Predict using regression 
  - cumulative revinue : Predict using regression 
  - Runtime:  average of the same genre 
  - Certificates : mode of the same genre 
  - Rating   :   0 (it means no one rate this movie yet!) 
  - Votes   :  0 
  - english  :  majority 
  - multi_lang   : majority
  - us   : majority
  - multi_country   : majority
  - month : choose randomly between top 3 months.
  - year :  fill with mode  
  
## Feature engineering

### Dealing with categorical data:
- Genre: add all Genres as columns and use like dummies
- Production company: take top 15 and add other and get dummies
- Cast, director, writer .. etc: generate representative weight values to reflect the persons’ power depending on the previous award nomination and wining.
### Adding useful columns:
-	Separate date to year and month 
- Language (Making a Boolean column to represent English and a column to represent other languages)
- Country (Making a Boolean column to represent USA and a column to represent other countries)


