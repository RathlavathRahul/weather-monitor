# Real-Time Weather Monitoring System

This project is a real-time data processing system that continuously monitors weather conditions for major metros in India and provides summarized insights through daily rollups and alerts based on user-defined thresholds. Data is collected from the OpenWeatherMap API, processed in real-time, and stored in a database for historical analysis.

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Dependencies](#dependencies)
- [System Requirements](#system-requirements)
- [Installation and Setup](#installation-and-setup)
- [Environment Variables](#environmental-variables)
- [Running the Application](#Running-the-application)
- [API Endpoints](#API-endpoints)
- [Scheduled Tasks](#schedules_tasks)
- [License](#License)

---

## Features

- Real-Time Weather Data Fetching: Automatically fetches weather data for specified cities every 5 minutes.
- Data Processing and Storage: Converts temperature to Celsius, saves data to MongoDB, and calculates daily rollups.
- Alerts for Extreme Conditions: Triggers alerts when temperatures exceed specified thresholds.
- Daily Summaries: Provides average, max, min temperatures, and the dominant weather condition for each city daily.

  ---

## Tech Stack

- Node.js: The server-side runtime used to build this backend.
- Express: A web application framework for setting up RESTful endpoints.
- MongoDB: A NoSQL database for storing weather data in JSON-like format.
- Docker: Containerization platform used to deploy MongoDB as a container.
- OpenWeatherMap API: The weather data source for real-time weather information.

---

## Dependencies
- dotenv: Loads environment variables from a .env file into process.env.
- express: Lightweight Node.js framework for setting up server and API endpoints.
- mongoose: Provides MongoDB object modeling for Node.js.
- axios: Used to make HTTP requests to the OpenWeatherMap API.
- node-cron: Schedules recurring tasks, such as fetching weather data at regular intervals.

---

## System Requirements

- Node.js (v12 or higher)
- MongoDB instance (local or Docker container)
- OpenWeatherMap API key (sign up here for a free key)

---

## Installation and Setup

 1. **Clone the repository:**

 ``` bash
   git clone https://github.com/RathlavathRahul/Rule-Engine.git
   cd backend
   ```

2. **Install Dependencies:**

```
npm install
```

---

## Environment Variables

Create a .env file in the root directory and add the following variables:

```
   OPENWEATHERMAP_API_KEY=4d428df7582caa7f253d661940e68032
   MONGO_URI="mongodb+srv://rathlavathrahul3276:Rahul@cluster0.oo6ux.mongodb.net/userDB?retryWrites=true&w=majority&appName=Cluster0"
   PORT=5000
```

---

## Running the Application

1. **Start the server with:**
```bash
   node app.js
   ```

   The server will run on http://localhost:5000.

   2. **Start the frontend app:**
     
```bash
npm start
   ```

   The React app will run on http://localhost:3000.

   ---

   ## API Endpoints

  - GET /summary/:city
- **Description:** Fetches a daily weather summary for the specified city.
- **Parameters**: city - The city for which the summary is requested (e.g., Delhi, Mumbai).

- **Response:**
  ```json
  {
  "avgTemp": 25.5,
  "maxTemp": 30,
  "minTemp": 20,
  "dominantWeather": "Clear"
  }
  ```

  ---

## Scheduled Tasks
The application uses node-cron to fetch weather data every 5 minutes for six major Indian cities (Delhi, Mumbai, Chennai, Bangalore, Kolkata, Hyderabad). The scheduled task:

- Fetches data for each city.
- Saves the weather data in MongoDB.
- Checks and logs alerts based on weather conditions.
- To modify the interval, adjust the cron schedule in the code:
  ```bash
  {
   cron.schedule('*/5 * * * *', async () => { /* tasks */ });
  }
  ```

---

## License
This project is licensed under the MIT License - see the LICENSE file for details.

---


