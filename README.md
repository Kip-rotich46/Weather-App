# Weather App Project.

## Introduction

This JavaScript application fetches the user's current location using the Geolocation API and retrieves weather data from the OpenWeatherMap API. The weather data is displayed on a webpage, including temperature, weather description, and timezone. Users can toggle between Celsius and Fahrenheit.

## Live Demo
https://kip-rotich46.github.io/Weather-App/

## Features

- Fetches the user's current geographical coordinates.
- Retrieves and displays weather information from the OpenWeatherMap API.
- Dynamically updates the DOM with the fetched weather data.
- Allows users to switch between Celsius and Fahrenheit.

## Requirements

- Browser with JavaScript enabled.
- Internet connection.
- Proxy server for handling CORS issues (e.g., CORS Anywhere).

## Setup and Installation

1. **HTML Structure**: Ensure the HTML file has the following elements with corresponding class names:

   ```html
   <div class="temperature">
     <span class="temperature-degree"></span>
     <span class="temperature span">F</span>
   </div>
   <div class="temperature-description"></div>
   <div class="location-timezone"></div>
   <canvas class="icon" width="128" height="128"></canvas>
   ```

2. **JavaScript File**: Include the JavaScript code in your HTML file or in an external `.js` file.

3. **Skycons Library**: Include the Skycons library in your HTML file:

   ```html
   <script src="https://darkskyapp.github.io/skycons/skycons.js"></script>
   ```

4. **CORS Proxy**: To avoid CORS issues, use a proxy service like CORS Anywhere. The proxy URL is included in the code.

## How to Use

1. **Load the Page**: When the page loads, the script will attempt to get the user's current geographical coordinates using the Geolocation API.
2. **Fetch Weather Data**: If geolocation is successful, the script will fetch weather data from the OpenWeatherMap API using the obtained coordinates.
3. **Display Weather Data**: The fetched weather data, including temperature, weather description, and timezone, will be displayed on the webpage.
4. **Toggle Temperature Units**: Click on the temperature section to toggle between Celsius and Fahrenheit.

## Code Breakdown

### Variables

- `long`, `lat`, `apiKey`: Store longitude, latitude, and API key respectively.
- `temperatureDescription`, `temperatureDegree`, `locationTimezone`, `temperatureSection`, `temperatureSpan`: DOM elements for displaying weather information.

### Geolocation API

- `navigator.geolocation.getCurrentPosition(position => {...})`: Retrieves the user's current position (latitude and longitude).

### OpenWeatherMap API

- `fetch(api).then(response => response.json()).then(data => {...})`: Fetches weather data from the OpenWeatherMap API and processes the JSON response.

### DOM Manipulation

- Updates the text content of `temperatureDegree`, `temperatureDescription`, and `locationTimezone` elements with the fetched weather data.

### Temperature Conversion

- Formula for converting Fahrenheit to Celsius: `let celsius = (temperature - 32) * (5 / 9)`.
- Event listener on `temperatureSection` to toggle between Celsius and Fahrenheit.

### Skycons

- `setIcons(icon, iconID)`: Uses the Skycons library to set weather icons.

### Example Usage

1. Ensure your HTML file has the required structure.
2. Include the Skycons library.
3. Add the JavaScript code to your HTML file.
4. Load the webpage and allow location access when prompted.

## Notes

- Replace `'2f426dfbb97966e6c1a480c7812f06df'` with your own OpenWeatherMap API key.
- This code uses a proxy (`https://cors-anywhere.herokuapp.com/`) to handle CORS issues. Ensure this service is available or use your own proxy server.
- Ensure your browser supports the Geolocation API.

## Troubleshooting

- **Geolocation Permission Denied**: Ensure the user allows location access.
- **CORS Issues**: Verify the proxy server is functioning or use a different proxy solution.
- **API Key Issues**: Ensure the API key is correct and has not expired or reached its usage limit.

## Conclusion

This weather app fetches and displays weather data based on the user's current location. It is a simple yet powerful example of integrating various web APIs to create a dynamic and interactive user experience.
