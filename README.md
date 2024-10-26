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
- [Alerts](#alerts)
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

