---
title: "Building a Dynamic Weather Application using the JavaScript DOM"
seoTitle: "Building a Dynamic Weather Application using the JavaScript DOM"
datePublished: Thu Feb 02 2023 04:22:14 GMT+0000 (Coordinated Universal Time)
cuid: cldmlcnna000209mobctpdvvo
slug: building-a-dynamic-weather-application-using-the-javascript-dom
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1675275267928/03eb476d-2459-4870-b31b-fd58097f8b66.jpeg
tags: programming-blogs, javascript, web-development, dom, wemakedevs

---

### Introduction

The Document Object Model (DOM) is a programming interface for HTML and XML documents. It allows developers to manipulate HTML and XML documents as objects and make dynamic updates to the content, structure, and style of a website. In this tutorial, we’ll be building a dynamic weather application using JavaScript DOM to demonstrate how to interact with HTML and CSS.

### Prerequisites

Before you start this project, you should have a basic understanding of HTML, CSS, and JavaScript. If you are new to these technologies, it's recommended that you take a few introductory courses to familiarize yourself with these topics.

### Project Overview

The project is to create a dynamic weather application that will allow users to search for weather information for a specific location. The application will use the OpenWeatherMap API to retrieve data and display the current weather conditions and a five-day forecast for the selected location.

## Project Steps:

### 1\. Set up the HTML and CSS

Start by creating the HTML and CSS structure for the application. Create an HTML file with a header, main content area, and footer. In the main content area, create an input field for the user to enter a location, a button to search for the weather, and a container for the weather information. The CSS should be used to style the page and make it visually appealing.

```xml
<!DOCTYPE html>
<html>
<head>
	<title>Weather Application</title>
	<link rel="stylesheet" type="text/css" href="style.css">
</head>
<body>
	<header>
		<h1>Weather Application</h1>
	</header>
	<main>
		<input type="text" id="location">
		<button id="search">Search</button>
		<div id="weather"></div>
	</main>
	<footer>
		<p>Copyright © 2023</p>
	</footer>
	<script src="app.js"></script>
</body>
</html>
```

```css
header {
	background-color: #333;
	color: #fff;
	text-align: center;
	padding: 1rem;
}

main {
	display: flex;
	flex-direction: column;
	align-items: center;
	margin-top: 2rem;
}

input[type="text"] {
	width: 50%;
	padding: 0.5rem;
	font-size: 1.2rem;
	margin-bottom: 1rem;
}

button {
	background-color: #333;
	color: #fff;
	padding: 0.5rem 1rem;
	font-size: 1.2rem;
	cursor: pointer;
}

#weather {
	width: 50%;
	margin-top: 2rem;
	background-color: #ccc;
	padding: 1rem;
	text-align: center;
}

footer {
	background-color: #333;
	color: #fff;
	text-align: center;
	padding: 1rem;
	margin-top: 2rem;
}
```

### 2\. Retrieve the API Key from OpenWeatherMap

Go to [OpenWeatherMap's website](https://openweathermap.org/api) and sign up for a free account to get an API key. The API key will be used to retrieve weather data from their servers.

### 3\. Add JavaScript to Retrieve and Display Weather Data

Next, create a JavaScript file and add code to retrieve the weather data using the OpenWeatherMap API. The code should make an API call to retrieve the current weather conditions and a five-day forecast for the selected location. The weather data should then be displayed in the weather container.

```javascript
const locationInput = document.getElementById('location');
const search = document.getElementById('search');
const weather = document.getElementById('weather');
const API_KEY = 'YOUR_API_KEY';

search.addEventListener('click', function () {
	fetch(`https://api.openweathermap.org/data/2.5/weather?q=${locationInput.value}&appid=${API_KEY}`)
		.then(response => response.json())
		.then(data => {
			const currentWeather = data.weather[0].description;
			const currentTemp = Math.round(data.main.temp - 273.15);
			weather.innerHTML = `
				<p>Current weather: ${currentWeather}</p>
				<p>Current temperature: ${currentTemp}°C</p>
			`;
		})
		.catch(error => {
			weather.innerHTML = `<p>Error: ${error}</p>`;
		});
});
```

### 4\. Add Five-Day Forecast

To add a five-day forecast to the weather application, make another API call to retrieve the five-day forecast data. The code should display the date, temperature, and weather conditions for each day.

```javascript
const forecast = document.createElement('div');
forecast.id = 'forecast';
weather.appendChild(forecast);

search.addEventListener('click', function () {
	fetch(`https://api.openweathermap.org/data/2.5/forecast?q=${location.value}&appid=${API_KEY}`)
		.then(response => response.json())
		.then(data => {
			const currentWeather = data.list[0].weather[0].description;
			const currentTemp = Math.round(data.list[0].main.temp - 273.15);
			weather.innerHTML = `
				<p>Current weather: ${currentWeather}</p>
				<p>Current temperature: ${currentTemp}°C</p>
			`;
			forecast.innerHTML = '';
			for (let i = 1; i <= 5; i++) {
				const date = new Date(data.list[i].dt * 1000).toDateString();
				const temp = Math.round(data.list[i].main.temp - 273.15);
				const condition = data.list[i].weather[0].description;
				forecast.innerHTML += `
					<p>${date}: ${temp}°C, ${condition}</p>
				`;
			}
		})
		.catch(error => {
			weather.innerHTML = `<p>Error: ${error}</p>`;
		});
});
```

### 5\. Test the Weather Application

Finally, test the weather application by entering a location and clicking the search button. The current weather conditions and five-day forecast should be displayed in the weather container.

**Here is a link to the code on GitHub**[https://github.com/bonaventureogeto/Zindua-JavaScript/tree/main/weather-app](https://github.com/bonaventureogeto/Zindua-JavaScript/tree/main/weather-app). **Star** the repository and fork to contribute and show support.

Congratulations, you have created a weather application using JavaScript and the DOM! With these skills, you can create dynamic and interactive web applications.

### Conclusion

The DOM (Document Object Model) is an essential part of web development and a crucial concept to understand in order to create dynamic and interactive web applications. This tutorial introduced the basics of the DOM and demonstrated how to use JavaScript to manipulate and access elements on a web page.

With this knowledge, you can build amazing web applications that engage users and provide valuable experiences.

I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)

Happy hacking!

### **To support these free courses,**[***buy me a coffee***](https://www.buymeacoffee.com/bonaogeto)***|| Share & Like***