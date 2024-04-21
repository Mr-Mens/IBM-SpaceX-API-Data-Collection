# SpaceX Falcon 9 First Stage Landing Prediction: Data Collection Lab

## Overview

This repository contains resources and instructions for predicting the landing success of SpaceX's Falcon 9 rocket's first stage. Given the significant cost reduction associated with reusing the rocket's first stage, accurately predicting landing outcomes can have substantial financial implications. This lab facilitates the collection and initial processing of SpaceX launch data to support such predictions.

## Repository Contents

- `README.md` - Instructions and information about this project.
- `extract_data.py` - Python script for data extraction from the SpaceX API.
- `requirements.txt` - List of Python packages required to run the script.

## Prerequisites

Before you begin, ensure you have Python installed on your machine (Python 3.8+ recommended). You will also need to install the necessary Python libraries:

```bash
pip install -r requirements.txt
```

## Lab Objective

The goal of this lab is to retrieve and preprocess data regarding Falcon 9 launches, focusing on the first stage landings. You will interact with the SpaceX API to fetch data, perform preliminary data cleaning, and structure the data for further analysis.

### Estimated Time to Complete: 45 minutes

## Instructions

### Step 1: Set Up Your Environment

Clone the repository to your local machine and install the required Python packages:

```bash
git clone https://github.com/your-username/spacex-falcon9-landing-prediction.git
cd spacex-falcon9-landing-prediction
pip install -r requirements.txt
```

### Step 2: Data Collection

Run the `extract_data.py` script to begin data extraction:

```bash
python extract_data.py
```

This script performs the following operations:
- Makes GET requests to the SpaceX API to fetch past launch data.
- Extracts relevant features from the JSON response.
- Uses auxiliary functions to further enrich the data (e.g., booster version, payload mass).
- Cleans and formats the data into a structured format.

### Step 3: Explore the Data

After running the script, explore the outputted CSV file to understand the dataset's structure and the variables involved:

```bash
import pandas as pd
data = pd.read_csv('dataset_part_1.csv')
print(data.head())
```

### Task Highlights

1. **API Interaction:** Fetch data about Falcon 9 launches using the SpaceX API.
2. **Data Parsing:** Convert JSON responses into a structured Pandas DataFrame.
3. **Data Wrangling:** Clean the data to handle missing values and extract additional information using defined helper functions.

## Example Outputs

You can expect the following outputs from the data collection script:

- `dataset_part_1.csv`: A CSV file containing structured data about Falcon 9 launches, including details about the booster version, payload mass, launch site, and landing outcomes.

## Data Fields

The dataset includes the following fields:

- `FlightNumber`: The unique identifier for the launch.
- `Date`: The date of the launch.
- `BoosterVersion`: The version of the Falcon 9 booster used.
- `PayloadMass`: The mass of the payload in kilograms.
- `Orbit`: The target orbit for the payload.
- `LaunchSite`: The geographical location of the launch.
- `Outcome`: The result of the landing attempt.
- `Flights`: The number of flights undertaken by the booster.
- `GridFins`: Indicates whether grid fins were used.
- `Reused`: Indicates whether the booster was reused.
- `Legs`: Indicates whether the landing legs were deployed.
- `LandingPad`: The specific landing pad used, if any.
- `Block`: The block number of the booster, representing its version.
- `ReusedCount`: The number of times the booster has been reused.
- `Serial`: The serial number of the booster.
- `Longitude`: The longitude of the launch site.
- `Latitude`: The latitude of the launch site.

## Authors

[Joseph Santarcangelo](https://www.linkedin.com/in/joseph-s-50398b136/) - PhD in Electrical Engineering, specializes in machine learning and computer vision. Joseph is currently a data scientist at IBM.

## Change Log

| Date (YYYY-MM-DD) | Version | Changed By      | Change Description               |
|-------------------|---------|----------------|----------------------------------|
| 2020-09-20        | 1.0     | Joseph          | Initial creation of the lab.     |
| 2021-01-20        | 1.1     | Joseph & Azim   | Updated the script for API calls and data extraction. |

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE.md) file for details. 

Feel free to fork this project, submit pull requests, or suggest improvements via issues. Happy data hunting!
