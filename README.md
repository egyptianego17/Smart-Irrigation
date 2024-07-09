# Smart Irrigation System

This project automates the irrigation process using sensor data and the Tuya IoT platform. The system checks soil moisture levels and controls the irrigation based on predefined conditions.

## Table of Contents

- [Installation](#installation)
- [Database Initialization](#database-initialization)
- [Running the Project](#running-the-project)
- [Configuration](#configuration)

## Installation

1. **Clone the repository:**

    ```sh
    git clone https://github.com/yourusername/smart-irrigation-system.git
    cd smart-irrigation-system
    ```

2. **Create and activate a virtual environment:**

    ```sh
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. **Install dependencies:**

    ```sh
    pip install -r requirements.txt
    ```

4. **Create a `.env` file:**

    Copy the example `.env.example` to `.env` and fill in the required values:

    ```sh
    cp .env.example .env
    ```

## Database Initialization

1. **Start MongoDB:**

    Make sure MongoDB is installed and running. If you don't have MongoDB installed, you can follow the [installation guide](https://docs.mongodb.com/manual/installation/).

2. **Create a new database and collection:**

    You can use the MongoDB shell or a GUI tool like MongoDB Compass to create a new database and collection. The default names used in this project are specified in `config/settings.py`:

    ```python
    MONGO_URI = 'your_mongo_uri'
    DB_NAME = 'your_database_name'
    COLLECTION_NAME = 'your_collection_name'
    ```

    Replace these placeholders with your actual database details.

## Running the Project

1. **Ensure the `.env` file is properly configured with your Tuya IoT credentials:**

    ```env
    API_REGION=your_api_region
    API_KEY=your_api_key
    API_SECRET=your_api_secret
    ```

2. **Run the main script:**

    ```sh
    python main.py
    ```

    This will start the process that reads sensor data, updates the database, and controls the irrigation system.

## Configuration

The project configuration is managed through environment variables and the `config/settings.py` file. Ensure that you have the following settings correctly configured:

- **MongoDB Settings:**

    ```python
    MONGO_URI = 'your_mongo_uri'
    DB_NAME = 'your_database_name'
    COLLECTION_NAME = 'your_collection_name'
    ```

- **Devices:**

    Define your devices in the `config/settings.py` file with their respective IDs from the Tuya IoT Platform:

    ```python
    DEVICES = {
        'Luminance sensor': 'your_luminance_sensor_id',
        'Smart soil sensor': 'your_smart_soil_sensor_id',
        'Irrigation controller': 'your_irrigation_controller_id'
    }
    ```
