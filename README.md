
# 🌦️ Weather API - Flask & PostgreSQL with Connection Pooling

A robust RESTful API built with Flask that integrates with the OpenWeatherMap API to fetch live weather data. This project demonstrates clean code principles, database connection pooling for high performance, and automated API documentation.

## 🚀 Key Features
- **Live Data Fetching:** Real-time integration with OpenWeatherMap.
- **Connection Pooling:** Uses `psycopg2.pool.SimpleConnectionPool` for efficient database resource management.
- **Modular Design:** Clear separation between API routes (`app.py`) and database logic (`db_config.py`).
- **Interactive Documentation:** Fully documented using Swagger UI (Flasgger).
- **CRUD Operations:** Supports saving live data and retrieving historical logs.

---

## 🛠️ Tech Stack
- **Backend:** Python, Flask
- **Database:** PostgreSQL
- **Documentation:** Swagger / Flasgger
- **Libraries:** `requests`, `psycopg2-binary`, `flask`

---

## 📂 Project Structure
```text
weather_api_project/
├── venv/                 # Virtual environment (created via python -m venv venv)
├── .env                  # Environment variables (from your screenshot)
├── .gitignore            # Git ignore file (from your screenshot)
├── app.py                # Main Flask API code (with fetch/history routes)
├── db_config.py          # Database pooling and helper functions (CRUD/Fetch)
├── requirements.txt      # Dependencies (flask, flasgger, psycopg2-binary, requests)
└── README.md             # The documentation file below

=======
# Weather API

A professional RESTful API for fetching and storing weather data.

## Features

- 🌤️ Fetch live weather data from OpenWeatherMap API
- 💾 Store weather logs in PostgreSQL
- 📊 Retrieve historical weather data
- 📚 Interactive Swagger documentation
- 🔒 Secure environment variable configuration

## Setup

### 1. Clone the repository

git clone https://github.com/yourusername/weather-api-project.git
cd weather-api-project


### 2. Create virtual environment

python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

### 3. Install dependencies

pip install -r requirements.txt


### 4. Configure environment variables

Create a `.env` file in the project root:
```env


WEATHER_API_KEY=your_api_key
WEATHER_API_URL=


### 5. Create database table
```sql
CREATE TABLE weather_logs (
    id SERIAL PRIMARY KEY,
    city_name VARCHAR(100) NOT NULL,
    temp NUMERIC,
    humidity NUMERIC,
    recorded_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### 6. Run the application
```bash
python app.py
```

## API Endpoints

- `GET /` - Health check
- `POST /weather/fetch/<city>` - Fetch and store weather data
- `GET /weather/history/<city>` - Get weather history

## Documentation

Access Swagger UI at: `http://localhost:8089/apidocs/`

## Tech Stack

- **Backend**: Flask
- **Database**: PostgreSQL
- **API Documentation**: Flasgger (Swagger)
- **External API**: OpenWeatherMap

## License

