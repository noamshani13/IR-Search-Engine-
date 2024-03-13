# Project Overview
This repository contains code for a Flask-based RESTful API that serves as a search engine for Wikipedia articles. The search engine provides various endpoints to search articles based on different criteria and retrieve relevant information such as titles and IDs.

# Code Structure
The code is organized as follows:

- app.py: This is the main entry point of the application. It contains the Flask application definition along with routes for different endpoints.
- utils.py: This module contains utility functions used for text processing, TF-IDF computation, and other data manipulation tasks.
- requirements.txt: This file lists all the dependencies required to run the application. Install these dependencies using pip install -r requirements.txt.

# Functionality

**Search Endpoint (/search)**
- Description: This endpoint returns up to 100 search results for the provided query.
- Functionality: It tokenizes the query, filters out stopwords, computes TF-IDF scores for each term, and ranks documents based on the presence of query terms in the titles.

**Search Body Endpoint (/search_body)**
- Description: This endpoint returns up to 100 search results for the query using TF-IDF and cosine similarity based on the body of articles.
- Functionality: The body of articles is tokenized using a provided tokenizer, stopwords are removed, and TF-IDF scores are computed. Cosine similarity is used to rank documents.

**Search Title Endpoint (/search_title)**
- Description: This endpoint returns all search results containing a query word in the title, ordered by the number of distinct query words appearing in the title.
- Functionality: Titles are tokenized using a provided tokenizer, stopwords are removed, and documents are ranked based on the number of distinct query words in the title.

**Search Anchor Endpoint (/search_anchor)**
- Description: This endpoint returns all search results containing a query word in the anchor text of articles, ordered by the number of query words in the anchor text.
- Functionality: Anchor text is tokenized using a provided tokenizer, stopwords are removed, and documents are ranked based on the number of query words in the anchor text.

**PageRank Endpoint (/get_pagerank)**
- Description: This endpoint returns PageRank values for a list of provided Wikipedia article IDs.
- Functionality: PageRank values are computed for the provided article IDs.

**PageView Endpoint (/get_pageview)**
- Description: This endpoint returns the number of page views for each of the provided Wikipedia articles in August 2021.
- Functionality: Page view numbers are retrieved for the provided article IDs.

**Running the Application**
- To run the Flask application locally, execute the following command:
search_frontend.py
- The application will be available at http://localhost:8080.
