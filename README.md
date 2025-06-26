# Aigeon AI Google Play API

## Overview

The `aigeon-ai.google-play-api` repository provides a server implementation using the FastMCP framework to interact with the Google Play Store via the SerpApi. This server allows users to perform detailed searches on the Google Play Store, retrieving information about apps based on various parameters like search queries, categories, device types, and more. The server is designed to be flexible and efficient, supporting both synchronous and asynchronous operations.

## Features Overview

- **Google Play Store Search**: Perform comprehensive searches on the Google Play Store using a variety of parameters.
- **Flexible Query Parameters**: Supports search queries, country and language codes, app categories, device types, age ranges, pagination, and more.
- **Output Options**: Retrieve results in either JSON or HTML format.
- **Caching Control**: Option to disallow cached results for fresh data retrieval.
- **Asynchronous Support**: Ability to perform asynchronous operations for improved performance.
- **Enterprise Features**: Includes ZeroTrace mode for enhanced privacy in enterprise environments.

## Main Features and Functionality

The primary functionality of this server is encapsulated in the `search_google_play` function, which is exposed as a tool in the FastMCP framework. This function allows users to:

- **Search by Query**: Specify a search query to find relevant apps.
- **Filter by Country and Language**: Use two-letter country and language codes to localize search results.
- **Categorize by App Type**: Search within specific app store categories.
- **Device-Specific Searches**: Tailor searches for specific device types like phones, tablets, TVs, etc.
- **Age Range Filtering**: Filter apps based on age suitability, particularly useful for family categories.
- **Pagination Support**: Use tokens to navigate through paginated results.
- **Chart Type Specification**: Search for apps based on chart types, such as top-selling free apps.
- **Control Caching and Async Operations**: Decide whether to use cached results and whether to perform operations asynchronously.
- **Enterprise-Level Privacy**: Enable ZeroTrace mode for enhanced privacy in enterprise settings.

## API Endpoints or Main Functions Description

### `search_google_play`

This function serves as the core API endpoint for searching the Google Play Store. It constructs a request payload based on the provided parameters and sends a GET request to the SerpApi's Google Play endpoint. The function parameters include:

- `q`: Search query string.
- `gl`: Two-letter country code (default is 'us').
- `hl`: Two-letter language code (default is 'en').
- `apps_category`: App store category.
- `store_device`: Device type (e.g., 'phone', 'tablet').
- `age`: Age range filter, applicable when `apps_category` is 'FAMILY'.
- `next_page_token`: Token for pagination.
- `section_page_token`: Token for section pagination.
- `chart`: Chart type for app listings.
- `see_more_token`: Token for additional pagination.
- `no_cache`: Boolean to disallow cached results.
- `aasync`: Boolean for asynchronous operation.
- `zero_trace`: Boolean for enabling ZeroTrace mode.
- `output`: Output format, either 'json' or 'html'.

The function processes these parameters, removes any that are not provided, and sends the request to the SerpApi. Upon receiving a response, it raises an error if the request fails and returns the response in JSON format.

This server implementation is designed to be run using the FastMCP framework, which handles the transport and execution of the server logic. By default, it listens on port 9997, but this can be customized via command-line arguments.