Search Engine Readme
This repository contains a Flask application implementing a search engine using TF-IDF and cosine similarity for retrieving relevant Wikipedia articles. Below is the explanation of the code structure, organization, and functionality of each major piece in the implementation:

Code Structure
The code is organized into several sections:

Imports: Imports necessary libraries and modules including Flask, PySpark, NLTK, and Google Cloud Storage client.
Custom Flask App: Defines a custom Flask application class MyFlaskApp which overrides the run method to allow custom configuration options.
Global Variables: Defines global variables including inverted_body, which is used to store inverted indices for the Wikipedia articles.
Stopwords and Tokenization: Defines functions for removing stopwords, tokenizing text, and computing word counts.
TF-IDF Computation: Defines functions for computing TF-IDF values and listing documents based on TF-IDF scores.
Flask Routes:
/search: Handles search queries by returning the top 100 search results based on TF-IDF scores of the body of articles.
/search_body: Returns up to 100 search results for the query using TF-IDF and cosine similarity of the body of articles only.
/search_title: Returns all search results that contain a query word in the title of articles, ordered by the number of distinct query words in the title.
/search_anchor: Returns all search results that contain a query word in the anchor text of articles, ordered by the number of query words in the anchor text.
/get_pagerank: Returns PageRank values for a list of provided wiki article IDs.
/get_pageview: Returns the number of page views for each of the provided wiki articles in August 2021.
Functionality
The application provides search functionality allowing users to query Wikipedia articles.
It supports various types of searches including body search, title search, and anchor search.
The TF-IDF algorithm is used for ranking search results based on relevance.
PageRank values and page view counts are also provided for additional information.
Usage
To use the search engine, follow these steps:

Ensure all dependencies are installed (Flask, pyspark, nltk, google-cloud-storage).
Run the Flask application by executing the script.
Access the different search endpoints (/search, /search_body, /search_title, /search_anchor) with appropriate query parameters.
Optionally, retrieve PageRank values and page view counts using the /get_pagerank and /get_pageview endpoints respectively.
