### BASICS

## What is an API?

The full form of API is **Application Programming Interface**.
**Application**
An application is any software program or service. This could be a mobile app, a website, or a desktop program. For our example, let's consider a weather app on your smartphone.
**Programming**
Programming refers to writing code that tells the application how to perform specific tasks. This code is written by developers.
**Interface**
An interface is a way for different systems to interact with each other. In the context of an API, it’s the point of interaction where the application can access data or services from another software component.

Putting it all together: Application Programming Interface

An API allows different software applications to communicate with each other and share data or functionality. It defines the methods and data formats that applications can use to interact with each other.

**Example: Weather App Using a Weather API**
**Application**: Your weather app on your smartphone.
**Programming**: The developers of the weather app write code to fetch weather data.
**Interface**: The weather app uses an API provided by a weather service to get the data it needs.

**How it Works:**
**API Documentation:** The weather service provides API documentation that explains how to request weather data. For example, it might say that to get the current weather for a city, you need to send a request to https://api.weather.com/current?location=your_city.

**API Request:** The weather app makes a request to the API. If you want to know the weather in New York, the request might look like this:

```
GET https://api.weather.com/current?location=New_York
```

**API Response:** The weather service processes the request and sends back a response containing the weather data. The response might be in JSON format and look like this:

`{ "location": "New York", "temperature": "22°C", "condition": "Sunny" }`

**Displaying Data:** The weather app receives this data from the API and displays it to you in a user-friendly way.

**Tools and Rules:**
**Tools:** The endpoints (like https://api.weather.com/current) and methods (like GET) provided by the API.
**Rules:** The API documentation specifies how to format requests and what kind of responses to expect, ensuring consistent and reliable communication between the weather app and the weather service.
This example illustrates how an API serves as a bridge, enabling your weather app (the application) to fetch and display up-to-date weather information by interacting with the weather service's server.
