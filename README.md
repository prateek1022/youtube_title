# YouTube Title Project

This project is a Node.js application designed to interact with the YouTube Data API to automatically update the title of a specific YouTube video.

## Features:

*   **Automated Title Updates**: Uses `node-cron` to schedule regular updates to a YouTube video's title.
*   **YouTube Data API Integration**: Leverages the `googleapis` library to authenticate and interact with the YouTube Data API (v3).
*   **OAuth2 Authentication**: Handles OAuth2 authentication flow to get user consent and store access tokens for API calls.
*   **Dynamic Title Generation**: The video title is dynamically updated to include current statistics such as:
    *   Number of views
    *   Number of likes
    *   Number of comments
*   **Configurable Video ID**: Targets a specific video for updates, defined by `VIDEO_ID`.

## Project Structure:

*   `index.js`: The main application file containing the core logic for authentication, API calls, and cron scheduling.
*   `client_secret.json`: Stores the OAuth 2.0 client credentials for accessing the Google API.
*   `package.json`: Defines project metadata, scripts, and dependencies (`google-auth-library`, `googleapis`, `node-cron`).

## Setup and Usage:

1.  **Google API Credentials**: Obtain your `client_secret.json` from the Google Cloud Console, enabling the YouTube Data API.
2.  **Dependencies**: Install project dependencies using `npm install`.
3.  **Authentication**: Run `node index.js` to initiate the OAuth2 flow. You will be prompted to authorize the application via a URL and enter a verification code.
4.  **Automated Updates**: Once authenticated, the application will automatically update the specified YouTube video's title at regular intervals (currently every 10 seconds as configured in `index.js`).

**Note**: The `client_id` and `client_secret` in `client_secret.json` have been intentionally set to "thisisascweretkey" for demonstration or placeholder purposes. You will need to replace these with your actual credentials for the application to function correctly.
