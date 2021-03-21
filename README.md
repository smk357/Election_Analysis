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
- Votes by county are as follows (with sample script used to determine this result):
   
   1. Jefferson: 10.5% (38,855)
   2. Denver: 82.8% (306,055)
   3. Arapahoe: 6.7% (24,801)
~~~
for row in reader:
  if county_name not in county:
      county.append(county_name)
      county_votes[county_name]=0
  county_votes[county_name]+=1
~~~
- Denver had the largest turnout at 306,055 votes cast. Sample script as follows:
~~~
for county_name in county_votes:
   county_turnout=county_votes[county_name]
   if county_turnout>largestcounty_turnout:
      largest_county=county_name
      largestcounty_turnout=county_turnout
~~~
- Votes by candidate are as follows (determined using script similar to that used for votes by county):
   1. Charles Casper Stockham: 23.0% (85,213)
   2. Diana DeGette: 73.8% (272,892)
   3. Raymon Anthony Doane: 3.1% (11,606)
 - The winning candidate was Diana DeGette with 73.8% of the vote and 272,892 votes cast (determined using script similar to that used for the largest county)
