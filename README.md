# IR-Search-Engine-
The Search Engine Project in IR Course

## Code Structure and Organization

The provided code consists of a Flask application (`MyFlaskApp`) implementing several endpoints for searching and retrieving information from a dataset. Here's a breakdown of the code structure:

- **Flask Application (`MyFlaskApp`):**
  - This class extends the Flask framework's `Flask` class to create a custom Flask application.
  - It includes custom configurations and settings for the Flask app.

- **Initialization and Utility Functions:**
  - `init_indexex()`: Initializes indexes required for search functionality. It loads inverted index data from Google Cloud Storage using the Google Cloud Storage Python Client.
  - `word_count(text, id)`: Tokenizes the text, filters out stopwords, and computes term frequencies.
  - `list_of_docid_and_title(query)`: Retrieves a list of document IDs and titles based on a search query using TF-IDF scoring.
  - Other utility functions for different types of searches like body search, title search, and anchor text search.

- **Flask Endpoints:**
  - `/search`: Endpoint for issuing a search query and retrieving up to 100 search results based on TF-IDF scoring.
  - `/search_body`: Endpoint for searching within the body of articles using TF-IDF and cosine similarity.
  - `/search_title`: Endpoint for searching within article titles, ordered by the number of distinct query words.
  - `/search_anchor`: Endpoint for searching within anchor text of articles, ordered by the number of query words in the anchor text.
  - `/get_pagerank`: Endpoint for retrieving PageRank values for a list of provided wiki article IDs.
  - `/get_pageview`: Endpoint for retrieving the number of page views for provided wiki article IDs in August 2021.

## Functionality

- **Search Endpoints (`/search`, `/search_body`, `/search_title`, `/search_anchor`):**
  - These endpoints accept a query parameter and return relevant search results based on different criteria such as TF-IDF scoring, body text similarity, title matching, and anchor text matching.
  - The search algorithms are implemented to return the most relevant results based on the specific requirements mentioned in the docstrings.

- **Data Retrieval Endpoints (`/get_pagerank`, `/get_pageview`):**
  - These endpoints accept a list of wiki article IDs and return PageRank values and page view numbers for the provided article IDs, respectively.
  - The data is retrieved based on the input article IDs and may involve querying external data sources.

## Running the Application

- The Flask application is configured to run on host `0.0.0.0` and port `8080`.
- To run the application, execute the script, and the Flask RESTful API will be accessible via the specified host and port.
- External services such as Google Cloud Storage might be required for certain functionalities, and appropriate configurations should be set up.

