# Description:

This is the welcome screen for "Opportunity," an application designed to manage and display upcoming events or tasks. The screen fetches data from a Google Sheets document and displays it in a sorted order based on the remaining time until each event. If there are no events available, it displays a default image.

## Setup Instructions:

## Dependencies:

### Vue.js: This project utilizes Vue.js for reactive and component-based UI development. Make sure Vue.js is installed in your environment.
Environment Variables:

### Set up environment variables for your Google Sheets API credentials:
VITE_GOOGLE_SHEET_ID: The ID of the Google Sheet containing event data.
VITE_GOOGLE_API_KEY: Your Google API key with access to Google Sheets API.
Installation:

Clone this repository to your local machine.
Navigate to the project directory and install dependencies using npm install or yarn install.
Running the Application:

Run the application using npm run dev or yarn dev.
Access the welcome screen through the provided URL.
Components:

### BaseHeader (Component):

Displays the title "Welcome to Opportunity" as the header of the page.
CardText (Component):

Represents each event as a card with the following details:
Event title (cardTitle).
Date (date).
Time (time).
Description text (text).
Remaining time until the event (remainingTime).
BaseFooter (Component):

Represents the footer of the page. (Details not provided in the code snippet.)

## Functionality:

### Data Fetching:

Fetches event data from a Google Sheets document using the Google Sheets API.
Automatically updates data every 30 minutes.
Event Sorting:

Sorts events based on the remaining time until each event occurs.
If events have the same remaining time, they are sorted based on the event time.
Conditional Rendering:

Displays event cards if data is available.
Displays a default image if no events are available.
Styling:

### Background:

Sets a background color for the main section.
Image Display:

Utilizes CSS to ensure that the background image covers the entire screen.
Note:

This README provides an overview of the welcome screen component of the Opportunity application. For detailed information on other components, features, and functionalities, refer to the corresponding documentation or codebase.
Author:
[Your Name or Organization]



## Technoligy used:
HTML5
Webpack
Responsive design
Flex
Git
JavaScript
JSON
VueJS

## Features:

Objects are sorted by Remaing Time and The Time and meeting-time

### Github :

https://github.com/wojtek-strzyzowski/welcomescreen-vue.git