##DevOps Assignment 1 

# AWS API Gateway – Level 1 (Manual Console Implementation)

## Project Overview

This project demonstrates manual configuration of AWS API Gateway using the AWS Console.

Three APIs were created manually:

1. `/json/{proxy+}` → Proxies to JSONPlaceholder API
2. `/weather` → Fetches weather data from Open-Meteo API
3. `/countries/{name}` → Fetches country details from RestCountries API

All configuration was done using AWS Management Console.

# Invoke URL

`https://0gl73iaji1.execute-api.ap-south-1.amazonaws.com/v1`

# Prerequisites

- AWS Account
- IAM user with API Gateway permissions
- Basic understanding of REST APIs

# Manual Configuration Steps

## 1️⃣ Create REST API
- Create new REST API
- Endpoint type: Regional

## 2️⃣ Configure `/json/{proxy+}`

- Create resource `/json`
- Create child resource `{proxy+}`
- Create GET method
- Integration type: HTTP Proxy
- Endpoint: `https://jsonplaceholder.typicode.com/{proxy}`
- Enable path parameter mapping

## 3️⃣ Configure `/weather`

- Create resource `/weather`
- Create GET method
- Integration type: HTTP
- Endpoint: `https://api.open-meteo.com/v1/forecast`
- Add query string parameters:
  - latitude (required)
  - longitude (required)
  - hourly (optional)
- Map query parameters in Integration Request

## 4️⃣ Configure `/countries/{name}`

- Create resource `/countries`
- Create child resource `{name}`
- Create GET method
- Integration type: HTTP
- Endpoint: `https://restcountries.com/v3.1/name/{name}`
- Enable path parameter mapping

## 5️⃣ Deploy API

- Create Stage: `v1`
- Deploy API

# Testing the APIs (examples)

## JSON API

```
curl.exe https://0gl73iaji1.execute-api.ap-south-1.amazonaws.com/v1/json/posts/2
```
---

## Weather API

```
curl.exe "https://0gl73iaji1.execute-api.ap-south-1.amazonaws.com/v1/weather?latitude=12&longitude=77&hourly=temperature_2m"
```

## Countries API

```
curl.exe https://0gl73iaji1.execute-api.ap-south-1.amazonaws.com/v1/countries/india
```

# 📸 Screenshots

Screenshots are included in the `screenshots/` folder:

- API resource tree
- JSON method configuration
- Weather integration configuration
- Countries integration configuration
- Stage deployment screen
- Curl output examples

---

# Concepts Demonstrated

- AWS API Gateway manual configuration
- HTTP Proxy integration
- Path parameters
- Query string parameter mapping
- API deployment stages

# Author

Thariq T
