```markdown
# Aigeon AI Google Play API

## Project Overview

The **Aigeon AI Google Play API** is a Python-based server application designed to facilitate seamless interaction with the Google Play Store using the SerpApi service. This project leverages the FastMCP framework to provide an efficient and scalable solution for querying Google Play Store data, enabling users to search for apps based on various parameters.

## Features Overview

- **Integration with SerpApi**: Utilizes the SerpApi service to perform searches on the Google Play Store.
- **Flexible Query Parameters**: Supports a wide range of search parameters, allowing for detailed and specific queries.
- **Pagination Support**: Handles pagination through tokens to navigate through search results efficiently.
- **Output Customization**: Offers options to receive results in either JSON or HTML format.
- **Environment Configuration**: Loads configuration settings from environment variables for secure and dynamic setup.

## Main Features and Functionality

### 1. Search Functionality

The core functionality of this application is to perform searches on the Google Play Store using the `search_google_play` function. This function allows users to specify various parameters to tailor their search queries, such as:

- **Search Query (`q`)**: A string parameter to specify the search term.
- **Country and Language Codes (`gl`, `hl`)**: Two-letter codes to define the geographical and language preferences for the search.
- **App Category (`apps_category`)**: Allows filtering of apps based on specific categories.
- **Device Type (`store_device`)**: Filters results based on the type of device, such as phone, tablet, or TV.
- **Age Range (`age`)**: Applicable when filtering apps within the FAMILY category.
- **Pagination Tokens (`next_page_token`, `section_page_token`, `see_more_token`)**: Tokens to manage and navigate through paginated results.
- **Chart Type (`chart`)**: Specifies the type of chart, such as top-selling free apps.
- **Cache Control (`no_cache`)**: Option to disable cached results for fresh data retrieval.
- **Async Mode (`aasync`)**: Enables asynchronous operation for improved performance.
- **Output Format (`output`)**: Determines the format of the search results, either JSON or HTML.

### 2. Server Initialization

The application initializes a FastMCP server instance named `google-play-server`, which listens for incoming requests and processes them using the defined search functionality. The server can be executed with a specified port, defaulting to port 9997 if not provided.

## Main Functions Description

### `search_google_play`

This function is the primary tool for interacting with the Google Play Store. It constructs a request payload based on the provided parameters, ensuring only non-null values are included. The function then sends a GET request to the SerpApi endpoint and returns the search results in the specified format. The function is annotated with detailed descriptions for each parameter, ensuring clarity and ease of use.

By leveraging this function, users can perform comprehensive searches on the Google Play Store, tailored to their specific needs and preferences, while benefiting from the robust infrastructure provided by the FastMCP framework and SerpApi service.

---

This README provides a comprehensive overview of the Aigeon AI Google Play API project, detailing its features, functionality, and usage. For further information, please refer to the source code and documentation.
```