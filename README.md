<div align="center">

# Plataforma Inteligente AI

[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-3.0%2B-000000?logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Random%20Forest-F7931E?logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

Predictive machine learning microservice for urban emergency response fleet health monitoring and vehicle failure prevention.

</div>

## Table of Contents

- [About](#about)
- [Features](#features)
- [API Endpoints](#api-endpoints)
- [Built With](#built-with)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Team](#team)
- [License](#license)

## About

**Plataforma Inteligente AI** is the predictive artificial intelligence service of the Smart Urban Emergency Management Platform (SAMU / Emergency Fleet). The service exposes a REST API built with Flask that receives real-time vehicle telemetry data (OBD-II and mechanical sensor signals) collected from operational ambulances.

Using a pre-trained **Random Forest** classifier (`random_forest_ai4i_obd2.pkl`), the API predicts mechanical failure probabilities, classifies failure types (e.g. heat dissipation, power failure, tool wear), and flags emergency vehicles requiring immediate preventative maintenance before critical en-route breakdown happens.

## Features

- **Predictive Failure Scoring:** Real-time inference calculating failure probability from live OBD-II diagnostic parameters.
- **Automated Preprocessing Pipeline:** Validates and normalizes raw sensor readings (temperatures, rotational speeds, torque, wear metrics).
- **Lightweight High-Throughput REST API:** Built with Flask for rapid response times in emergency dispatch decision flows.
- **Health Check & Diagnostics:** Dedicated endpoint for orchestration monitoring and service readiness.

## API Endpoints

- `GET /` — API health check and operational status.
- `POST /prever` — Submits OBD-II telemetry features and receives failure classification and risk probability.

## Built With

- **Python 3.10+**
- **Flask** for REST API services
- **Scikit-Learn** for the Random Forest classifier
- **Pandas & NumPy** for feature transformations and matrix calculations
- **Joblib** for high-efficiency model persistence and deserialization

## Getting Started

### Requirements

- Python 3.10 or later
- `pip` package manager

### Installation & Run

1. Clone the repository:
   ```bash
   git clone https://github.com/hyauss/PlataformaInteligenteAI.git
   cd PlataformaInteligenteAI
   ```

2. Create and activate a virtual environment:
   - **macOS / Linux:**
     ```bash
     python3 -m venv venv
     source venv/bin/activate
     ```
   - **Windows:**
     ```bash
     python -m venv venv
     venv\Scripts\activate
     ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Launch the API server:
   ```bash
   python app.py
   ```

The API will be available at `http://localhost:5001`.

## Project Structure

```
PlataformaInteligenteAI/
├── app.py                      Flask application entry point and routing
├── requirements.txt            Python dependencies
├── modelo/
│   └── random_forest_ai4i_obd2.pkl Trained Random Forest classification model
└── services/
    ├── preprocessing.py        Input feature sanitization, bounds checking and transformation
    └── prediction_service.py   Model execution and probability scoring service
```

## Team

<div align="center">
  <table>
    <tr>
      <td align="center" width="25%">
        <a href="https://github.com/RafaelMRos"><img src="https://github.com/RafaelMRos.png" width="90" alt="Rafael M. Ros"/></a>
        <br/><sub><b>Rafael M. Ros</b></sub><br/><br/>
        <a href="https://github.com/RafaelMRos"><img src="https://skillicons.dev/icons?i=github" alt="GitHub"/></a>
      </td>
      <td align="center" width="25%">
        <a href="https://github.com/hyauss"><img src="https://github.com/hyauss.png" width="90" alt="Vinicius Marques"/></a>
        <br/><sub><b>Vinicius Marques</b></sub><br/><br/>
        <a href="https://github.com/hyauss"><img src="https://skillicons.dev/icons?i=github" alt="GitHub"/></a>
        <a href="https://www.linkedin.com/in/vinicius-marques-966918274/"><img src="https://skillicons.dev/icons?i=linkedin" alt="LinkedIn"/></a>
      </td>
    </tr>
  </table>
</div>

## License

Released under the [MIT License](LICENSE). Copyright (c) 2026 Rafael M. Ros and Vinicius Marques.
