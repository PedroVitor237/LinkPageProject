# Link Page Project

Link Page Project is a small, static frontend project with a profile/link page and a separate weather-and-time interface. It began as a learning exercise in the Mimo mobile app and was later expanded through experimentation with vanilla HTML, CSS, JavaScript, browser APIs, and asynchronous data fetching.

The project demonstrates foundational frontend skills without frameworks, dependencies, or a build step.

## Implemented Features

- A link page for the UEMA PROFITEC Systems Analysis and Development group, including an Instagram link and navigation to the weather project
- A two-page structure connected with standard HTML links
- A local time display generated when the weather page loads
- Morning, afternoon, and night images and page colors selected from the browser's local system time
- On-demand weather lookup for Itapecuru Mirim, Maranhao, Brazil
- Dynamic rendering of temperature and wind speed returned by Open-Meteo
- Custom CSS styling with a gradient, rounded elements, and panel shadows

## Technologies and Frontend Concepts

- HTML5 and CSS3
- Vanilla JavaScript
- DOM selection and dynamic `innerHTML`, image source, and inline style updates
- Inline load and click event handlers
- The browser `Date` API
- The Fetch API, Promise chaining, JSON response processing, and basic error logging
- The Open-Meteo Forecast API

## Weather API Integration

Weather data is requested only when the user selects the weather button. The project sends a `GET` request to Open-Meteo's `/v1/forecast` endpoint with these parameters:

- `latitude=-3.3096`
- `longitude=-44.2489`
- `current_weather=true`

The coordinates are hard-coded for Itapecuru Mirim. The response's `current_weather.temperature` and `current_weather.windspeed` values are displayed as degrees Celsius and kilometers per hour. The interface does not use browser geolocation or allow the user to choose another city.

The request is handled with `fetch()` and `.then()` Promise callbacks. Failures are logged to the browser console; there is currently no loading state or visible error message.

## Time-Based Interface

When the weather page loads, JavaScript reads the browser's local hour and minute with `new Date()`, writes the time to the page, and changes the weather page's image and background color:

- Morning: 06:00 through 11:59
- Afternoon: 12:00 through 18:59
- Night: 19:00 through 05:59

This behavior is entirely client-side and applies only to the weather-and-time page.

## Project Structure

```text
LinkPageProject/
├── LinkinPage/
│   ├── index.html
│   ├── style.css
│   ├── Images/
│   │   └── ads_logo.jpg
│   └── Weather_Project/
│       ├── weatherAndTime.html
│       ├── style.css
│       ├── script.js
│       └── ImagesWeather/
│           ├── leonardoPaisagemManh0.WebP
│           ├── leonardoPaisagemTarde2.WebP
│           └── leonardoPaisagemNoite3.WebP
├── LICENSE
└── README.md
```

## How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/PedroVitor237/LinkPageProject.git
   ```

2. Open `LinkinPage/index.html` in a web browser.

No installation, configuration, API key, or build tool is required. An internet connection and access to the Open-Meteo service are required for the weather lookup; the rest of the project runs locally.

## Current Status and Limitations

The implemented pages, time-based visual changes, navigation, and fixed-location weather request are functional learning-project features. Current limitations include:

- The WhatsApp link is a placeholder rather than a working profile URL.
- Weather sections use a fixed width and there are no responsive media queries, so the weather page may overflow on narrow screens.
- Weather is limited to one hard-coded location and is fetched manually.
- API errors are not shown in the page interface.

## Future Improvements

- Add responsive behavior for smaller screens.
- Improve the UI with refined layouts, hover states, and animations.
- Allow weather searches by city.

## Author

Pedro Vitor — [PedroVitor237](https://github.com/PedroVitor237)
