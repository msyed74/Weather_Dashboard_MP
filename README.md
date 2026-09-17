# 🌦️ Weather & Air Quality Analytics Dashboard | Power BI

An interactive **Weather & Air Quality Analytics Dashboard** built using **Microsoft Power BI**, **Power Query**, and **DAX**.

The dashboard provides a real-time-style overview of weather conditions, upcoming forecasts, precipitation chances, and major air pollutants through a clean and interactive visual interface.

---

## 📊 Dashboard Preview

![Weather & Air Quality Dashboard](./.png)

---

## 🎯 Project Objective

The objective of this project is to transform weather and environmental data into an intuitive analytical dashboard that enables users to quickly understand:

- Current weather conditions
- Temperature trends
- Upcoming weather forecasts
- Rain probability
- Air quality
- Major air pollutants
- Atmospheric conditions
- Sunrise and sunset timings

The project demonstrates practical skills in **data transformation, DAX calculations, data modeling, and dashboard design using Power BI**.

---

## ✨ Dashboard Features

### 🌡️ Current Weather

The dashboard displays important current weather indicators including:

- Current Temperature
- Weather Condition
- Humidity
- Wind Speed
- Visibility
- Atmospheric Pressure
- UV Index
- Precipitation

---

### 📈 Temperature Forecast

A multi-day temperature trend visualization provides an overview of expected temperature changes.

The forecast section includes:

- Daily temperature
- Temperature trend
- Multiple upcoming days
- Visual trend analysis

---

### 🌧️ Rain Forecast

The rainfall section displays the probability of rain for upcoming days.

It helps users understand:

- Chance of precipitation
- Forecasted temperature
- Daily rainfall probability
- Changes in precipitation conditions

---

### 🌅 Sunrise & Sunset

The dashboard provides:

- Sunrise time
- Sunset time

This information gives users a quick overview of daylight timings for the selected location.

---

## 🌍 Air Quality Analysis

The Air Quality section provides information about major atmospheric pollutants.

### Pollutants Analyzed

| Pollutant | Description |
|-----------|-------------|
| CO | Carbon Monoxide |
| PM10 | Particulate Matter |
| PM2.5 | Fine Particulate Matter |
| NO₂ | Nitrogen Dioxide |
| O₃ | Ozone |
| SO₂ | Sulfur Dioxide |

The dashboard presents pollutant concentrations alongside an air-quality visualization for quick interpretation.

---

## 🧮 DAX Implementation

DAX was used to create dynamic calculations and conditional status classifications.

### Example: AQI Status

```DAX
AQI Status Text =
VAR AQI =
    ROUND(
        SELECTEDVALUE(
            'Current'[current.air_quality.pm10],
            0
        ),
        0
    )
RETURN
    SWITCH(
        TRUE(),
        AQI <= 50, "GOOD",
        AQI <= 100, "MODERATE",
        AQI <= 150, "UNHEALTHY FOR SENSITIVE GROUPS",
        AQI <= 200, "UNHEALTHY",
        AQI <= 300, "VERY UNHEALTHY",
        "HAZARDOUS"
    )
