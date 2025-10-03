MLOps Capstone: Retail & Customer Analytics Platform
This repository contains the source code for an end-to-end MLOps project designed to deliver actionable insights from retail sales data. The system features an automated data pipeline, a machine learning model for customer segmentation, and a dual-interface for accessing insights via a REST API and an interactive web dashboard.

📋 Table of Contents
Project Overview
Key Features
Technology Stack
System Architecture
Project Structure
Getting Started
Prerequisites
Installation
Running the Application
API Endpoints
Dashboard Pages

🎯 Project Overview
The primary goal of this project is to build a robust and automated MLOps pipeline that transforms raw retail data into strategic business intelligence. The system ingests daily sales data, performs RFM-based customer segmentation using a K-Means clustering model, and analyzes key business metrics. These insights are then exposed through a scalable FastAPI backend and visualized in a user-friendly Streamlit dashboard, enabling data-driven decision-making for marketing and sales strategies.

✨ Key Features
Automated Data Pipeline: Ingests, cleans, and transforms raw sales data into an analysis-ready format.

ML-Powered Customer Segmentation: Implements RFM (Recency, Frequency, Monetary) analysis combined with K-Means clustering to categorize customers into meaningful segments (e.g., "Champions," "Loyal," "At Risk").

Store Performance Analytics: Delivers comparative insights on sales volume, revenue, and transaction counts across all retail locations.

Profitability & Discount Analysis: Calculates the net impact of discounts on sales revenue for each product category.

Seasonal Trend Identification: Analyzes monthly and quarterly sales patterns to uncover and visualize business seasonality.

Interactive Dashboard: A user-friendly web application built with Streamlit for visualizing key metrics, customer segments, and performance trends.

RESTful API: A scalable API built with FastAPI to programmatically serve processed data and analytics results.

Campaign ROI Simulator: An interactive tool to model the potential return on investment for marketing campaigns targeted at specific customer segments.

🛠️ Technology Stack
Category
Technologies
Backend
Python, FastAPI
Web Server
Uvicorn, Gunicorn
Dashboard
Streamlit
Data Science & ML
Pandas, Scikit-learn
Data Visualization
Plotly
Deployment
Procfile for Heroku, Render, or similar platforms

🏗️ System Architecture
The project follows a sequential data flow:

Data Ingestion: The data_processing.py script reads the raw customer_shopping_data.csv.

Data Processing & Modeling: The script cleans the data, performs RFM analysis, and applies a K-Means clustering model to segment customers. The enriched data is saved as processed_customer_data.parquet.

API Layer: The FastAPI application (api.py) loads the processed parquet file and exposes various endpoints to serve the data and insights.

Presentation Layer: The Streamlit dashboard (dashboard.py) consumes data from the FastAPI endpoints to create interactive visualizations and reports for the end-user.

📁 Project Structure
/MLOps_Capstone_Project/
|
|-- data/
|   |-- customer_shopping_data.csv      # Raw input dataset
|   |-- processed_customer_data.parquet # Processed and enriched output data
|
|-- src/
|   |-- __init__.py
|   |-- data_processing.py              # Script for data ingestion, cleaning, and transformation
|   |-- analysis.py                     # Core analytics and ML modeling functions
|   |-- api.py                          # FastAPI application (backend)
|   |-- dashboard.py                    # Streamlit application (frontend)
|
|-- Procfile                            # Deployment configuration for cloud platforms
|-- requirements.txt                    # Python package dependencies
|-- README.md                           # This file

🚀 Getting Started
Follow these instructions to set up and run the project on your local machine.

Prerequisites
Python (version 3.8 or higher)

pip package manager

Installation
Clone the Repository

git clone <your-repository-url>
cd MLOps_Capstone_Project

Create and Activate a Virtual Environment

Windows:

python -m venv venv
.\venv\Scripts\activate

macOS / Linux:

python3 -m venv venv
source venv/bin/activate

Install Dependencies

pip install -r requirements.txt

Running the Application
The project components must be run in the following order.

Step 1: Process the Data
Run the data processing script to generate the processed_customer_data.parquet file. This only needs to be done once.

python src/data_processing.py

Step 2: Start the FastAPI Server
Start the API server using Uvicorn. The --reload flag enables hot-reloading for development.

uvicorn src.api:app --reload

The API will be available at http://127.0.0.1:8000. Interactive documentation (Swagger UI) can be accessed at http://127.0.0.1:8000/docs.

Step 3: Launch the Streamlit Dashboard
In a new terminal, run the Streamlit application.

streamlit run src/dashboard.py

The dashboard will automatically open in your web browser, typically at http://localhost:8501.

🌐 API Endpoints
The FastAPI server provides the following endpoints to access the analytics data.

Method

Endpoint

Description

GET

/performance/stores

Get sales performance data for all stores.

GET

/customers/rfm-segments

Get RFM and K-Means segment data for all customers.

GET

/insights/seasonality

Get monthly and quarterly sales trend data.

GET

/insights/discount-impact

Get profitability and discount data by category.

GET

/customers/repeat-vs-onetime

Compare sales from repeat vs. one-time customers.

GET

/simulations/campaign

Run a campaign ROI simulation for a target segment.

📊 Dashboard Pages
The Streamlit dashboard is organized into the following pages for intuitive navigation:

Overview: A high-level summary of key metrics, including total sales, total customers, and overall store performance.

Customer Analysis: A deep dive into the customer segments generated by the K-Means model, with visualizations of their defining characteristics and business value.

Performance & Trends: Visual analysis of seasonal sales patterns and the impact of discounts on profitability.

Campaign Simulator: An interactive tool for strategists to model the financial outcome of marketing campaigns targeted at specific customer segments.
## Project Structure

API Link-[https://priyadharshini-d-mlops-capstone.onrender.com/docs]

Dashboard Link-[https://priyadharshini-d-mlops-dashboard.streamlit.app]





