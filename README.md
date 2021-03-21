# Election_Analysis
**An audit of Colorado Election Results

## Overview

The purpoose of the analysis was to help Tom, a representative of Colorado's electoral board, in certifying congressional election results for 3 counties. The data (election_results.csv) was divded by ballot ID, county, and candidate. The results required to certified were total votes cast, total votes cast by county and per candidate, and the percentage of the total votes for each county and candididate. The winning candidate and county with the highest turnout were also to be determined.

## Results

### Candidate list

- Charles Casper Stockham
- Diana DeGette
- Raymon Anthony Doane

### County List

- Jefferson
- Denver
- Arapahoe

### Election Outcome

- Total votes cast: 369,711. The total number of votes was determined by counting the number of rows after the header row using python:

~~~
with open(file_to_load) as election_data:
   reader = csv.reader(election_data)
   header = next(reader)
   for row in reader:
      total_votes = total_votes + 1
~~~


