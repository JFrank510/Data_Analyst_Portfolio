# Exercise using SQL/Python/Spark (EN)
I carried out a practice to improve my Python and SQL skills, incorporating the use of Spark as an additional tool.

## What the project consists of:
### Python
#### 1. Create a function called search that will search for any search term in the Wikipedia database and return the result of that query. Then execute the following:
- The function receives as its only input parameter: search_term, which represents the term to be searched.
- The function will have as output a JSON result called response_content with the API response content.
- Print the result on screen.
- Input (Type String): search_term
- Output (Type JSON): response_content

[Documentation](https://www.mediawiki.org/wiki/API:Search#GET_request)

For the following exercise, use the requests library of Python to connect to the Wikipedia RESTful API.

#### 2. Build a function called get_results_table that will take the output of the search function as input and output a Pandas library DataFrame. Then execute the following:
- The function receives as input parameter the output of the search function.
- The function will have as output a Pandas DataFrame called df.
- Remove the columns ns and snippet as a business rule.
- Add a column called search_term that contains the searched term.
- Print the result on screen.
- Save the result in a CSV file called salida.csv (If executed in Drive, it must be loaded into the /content folder).
- Input (Type String): output_call_search
- Output (Type Pandas Data Frame): df

### Spark
1. Create a function called main that builds a Spark DataFrame based on the previous CSV file. Then execute the following:
- The function receives as parameter: path, which is the path of the CSV file.
- The function will have as output a Spark DataFrame.
- Remove the columns ns and snippet as a business rule.
- Order the columns as follows: Title, Timestamp, Wordcount.
- Rename the columns while keeping the same order as in the previous point: Title, Date, Word Count.
- Order the table from the most recent data to the oldest based on the timestamp field.
- Print the result on screen.
- Input (Type String): path
- Output (Type JSON): df

### SQL
In this section, you will use two open-source datasets to answer some questions later: 
- flights.csv: contains 100k records of flights from the year 2015 within the United States.
- airports.csv: catalog of airports in the United States. 
Both datasets are available in Data.

Context:
The U.S. Department of Transportation's (DOT) Bureau of Transportation Statistics tracks the on-time performance of domestic flights operated by large airlines. Summarized information on the number of on-time, delayed, canceled, and diverted flights is published in the DOT's monthly Air Travel Consumer Report and in this dataset of flight delays and cancellations for 2015.

1. Make a record of the number of flights between an origin airport (origin_airport) and a destination airport (destination_airport) with departure delay (departure_delay) but arrived on time (arrival_delay). Add the name of the airport available in the airport field of the airports dataset.
2. Calculate the daily average flight time (air_time) between the route from San Francisco (origin_airport = 'SFO') and Los Angeles (destination_airport='LAX').
3. Find the airline and the most frequent cancellation reason for the flights that were cancelled in the year 2015. The FREQUENCY column indicates the most frequent cancellation reason for each airline, and can take one of the following values:
- A: meaning cancellation due to airline's operational reasons.
- B: meaning cancellation due to technical reasons.
- C: meaning cancellation due to safety reasons.
- D: meaning cancellation due to weather conditions.
    
    You should display the airlines that had the highest frequency of cancellations for each of these reasons. If there are multiple airlines with the same maximum frequency, the query should show all of them. The results should be ordered in descending order by the maximum cancellation frequency.
