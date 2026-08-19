# WebBasicsProjects

WebBasicsProjects is a collection of small, static frontend projects built while studying and experimenting with foundational web development. The work began in the Mimo mobile app and was later expanded with browser-based JavaScript, DOM updates, and external API consumption.

The repository currently contains two connected mini-projects. Each project has its own HTML, CSS, and assets, while the weather project also includes JavaScript. No frameworks, package dependencies, or build tools are used.

## Projects

### 1. Link Page

`LinkPage/` contains a profile and links page for the UEMA PROFITEC Systems Analysis and Development group. It includes:

- A group logo and short introduction
- An external Instagram link
- A placeholder WhatsApp link
- Navigation to the Weather and Time project
- Custom CSS with a gradient background, percentage-based image and link widths, rounded elements, and centered content

### 2. Weather and Time

`Weather_Project/` contains an interactive weather-and-time page. It includes:

- A local time message generated when the page loads
- Morning, afternoon, and night images selected according to the browser's local system time
- Matching background-color changes for each time period
- An on-demand weather request for Itapecuru Mirim, Maranhao, Brazil
- Dynamic display of the returned temperature and wind speed
- Navigation back to the Link Page

The time is read once on page load rather than updated continuously. The implemented time periods are:

- Morning: 06:00 through 11:59
- Afternoon: 12:00 through 18:59
- Night: 19:00 through 05:59

## Technologies and Concepts

- HTML5 and CSS3
- Vanilla JavaScript
- Basic semantic HTML elements and standard anchor navigation
- DOM element selection and `innerHTML` updates
- Dynamic image source and inline background-style changes
- Inline page-load and button-click event handlers
- Conditional rendering based on the browser `Date` API
- The Fetch API and Promise chaining with `.then()` and `.catch()`
- JSON response processing and basic console error logging
- Open-Meteo Forecast API integration

## Open-Meteo Integration

Selecting the weather button sends a `GET` request to Open-Meteo's `/v1/forecast` endpoint with:

- `latitude=-3.3096`
- `longitude=-44.2489`
- `current_weather=true`

The coordinates are hard-coded for Itapecuru Mirim. The interface reads `current_weather.temperature` and `current_weather.windspeed` from the JSON response and displays them in degrees Celsius and kilometers per hour.

The project does not use geolocation or provide city selection. There is no loading state or visible error message; request failures are logged only to the browser console.

## Repository Structure

```text
WebBasicsProjects/
├── LinkPage/
│   ├── index.html
│   ├── style.css
│   └── Images/
│       └── ads_logo.jpg
├── Weather_Project/
│   ├── weatherAndTime.html
│   ├── style.css
│   ├── script.js
│   └── ImagesWeather/
│       ├── paisagemManh0.WebP
│       ├── paisagemTarde2.WebP
│       └── paisagemNoite3.WebP
├── LICENSE
└── README.md
```

## How to Run

1. Clone the repository and enter its directory:

   ```bash
   git clone https://github.com/PedroVitor237/WebBasicsProjects.git
   cd WebBasicsProjects
   ```

2. Serve the repository root with a local static server. For example, with Python:

   ```bash
   python3 -m http.server 8000
   ```

3. Open either project:

   - Link Page: `http://localhost:8000/LinkPage/`
   - Weather and Time: `http://localhost:8000/Weather_Project/weatherAndTime.html`

Serving the repository root is important because navigation between the projects uses root-relative URLs. No installation, API key, or build step is required. The weather request requires an internet connection and access to Open-Meteo.

## Current Status and Limitations

Both mini-projects implement their core learning objectives, but they remain small experiments rather than production applications. Current limitations include:

- The WhatsApp destination is a placeholder.
- The weather page uses fixed-width sections and has no responsive media queries, so it may overflow on narrow screens.
- Weather is limited to one hard-coded location and is fetched only after a button click.
- The displayed time is not refreshed after the page loads.
- API errors are not displayed in the interface.
- Root-relative navigation assumes the repository is served from the web server's root.

## Future Improvements

- Add responsive behavior for smaller screens.
- Improve the interfaces with refined layouts, hover states, and animations.
- Allow weather searches by city.

## Author

Pedro Vitor — [PedroVitor237](https://github.com/PedroVitor237)
