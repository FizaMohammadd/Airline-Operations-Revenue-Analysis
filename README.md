# ✈️ Airline Operations & Revenue Analysis

## 📌 Project Overview

This project demonstrates a Python-based exploratory data analysis (EDA) workflow using airline operational data.

The analysis focuses on **seat occupancy, unused capacity, fares, bookings, routes, aircraft utilization, and ticket revenue** to identify patterns and areas that may require further business investigation.

---

## 🎯 Business Case

The airline is facing pressure from higher fuel costs, labour costs, taxes, financing costs, and stricter environmental requirements.

The business wants to improve **seat occupancy** and **revenue per available seat** so that unused capacity can be reduced.

This project analyzes available airline data to understand:

* How efficiently available seats are being utilized
* How occupancy varies across aircraft and routes
* How fares relate to occupancy
* How aircraft and routes contribute to revenue
* Where unused capacity may require further investigation

---

## 🎯 Key Business Questions

The analysis focuses on questions such as:

* Which aircraft types have the highest and lowest occupancy?
* Which aircraft types have the greatest available capacity?
* Does the most frequently used aircraft also have the highest occupancy?
* How does fare class affect average fare?
* Is average fare related to occupancy?
* Does occupancy vary by day of the week?
* Which aircraft generates the most ticket revenue?
* Which route-aircraft combinations have the greatest unused capacity?
* Which route-aircraft combinations should the business investigate first?
* What does a 10% occupancy improvement scenario suggest about revenue opportunity?

---

## 📊 Dataset

The project uses **8 airline CSV datasets**.

| Dataset               |       Records | Description                           |
| --------------------- | ------------: | ------------------------------------- |
| `aircrafts_data.csv`  |             9 | Aircraft types and range              |
| `airports_data.csv`   |           104 | Airport information                   |
| `boarding_passes.csv` |       579,686 | Passenger boarding records            |
| `bookings.csv`        |       262,788 | Booking information                   |
| `flights.csv`         |        33,121 | Scheduled flight information          |
| `seats.csv`           |         1,339 | Aircraft seat information             |
| `ticket_flights.csv`  | **1,045,726** | Ticket-to-flight and fare information |
| `tickets.csv`         |       366,733 | Ticket and passenger information      |

### Data Scale

The largest table, `ticket_flights.csv`, contains **1M+ ticket-flight records**.

After combining and aggregating the required tables, the analysis produces a **flight-level dataset containing 33K flights**, where each row represents one flight.

---

## 🛠️ Tools & Technologies

* **Python**
* **Pandas**
* **Matplotlib**
* **Jupyter Notebook**
* **GitHub**

---

## 🔄 Analysis Workflow

```text
8 Raw CSV Tables
       ↓
Data Inspection
       ↓
Data Cleaning & Preparation
       ↓
Table Aggregation & Integration
       ↓
Flight-Level Analytical Dataset
       ↓
Univariate EDA
       ↓
Bivariate EDA
       ↓
Multivariate EDA
       ↓
Occupancy & Revenue Analysis
       ↓
Low-Occupancy Opportunity Analysis
       ↓
Revenue Sensitivity Scenario
       ↓
Business Inferences & Recommendations
```

---

## 🧹 Data Preparation

The analysis includes:

* Inspecting dataset shape and columns
* Checking data types
* Identifying missing values
* Checking duplicates
* Converting date and time columns
* Aggregating tables before merging where required
* Combining the relevant datasets
* Creating a flight-level analytical dataset
* Calculating seat capacity
* Calculating passenger occupancy
* Calculating unused seats
* Calculating ticket revenue
* Calculating revenue per available seat
* Creating route, month, day-of-week, and departure-hour fields

### Occupancy Calculation

```text
Occupancy =
Boarded Passengers / Total Seats
```

### Revenue per Available Seat

```text
Revenue per Available Seat =
Ticket Revenue / Total Seats
```

---

## 📈 Exploratory Data Analysis

### Univariate Analysis

The analysis explores individual variables such as:

* Flight status
* Aircraft range
* Seat capacity
* Aircraft frequency
* Occupancy distribution
* Fare distribution
* Daily booking volume
* Daily booking value

### Bivariate Analysis

Relationships explored include:

* Aircraft vs Occupancy
* Fare Class vs Average Fare
* Fare vs Occupancy
* Day of Week vs Occupancy
* Occupancy vs Revenue
* Aircraft vs Revenue

### Multivariate Analysis

The analysis also examines:

* Route + Aircraft + Occupancy
* Route + Aircraft + Revenue per Available Seat

This helps move beyond individual variables and understand how multiple operational factors interact.

---

## 📊 Key Analysis Findings

### Aircraft Occupancy

Average occupancy varied considerably across aircraft types.

| Aircraft            | Average Occupancy |
| ------------------- | ----------------: |
| Bombardier CRJ-200  |             43.0% |
| Airbus A319-100     |             46.2% |
| Cessna 208 Caravan  |             50.0% |
| Boeing 767-300      |             51.3% |
| Airbus A321-200     |             52.2% |
| Sukhoi Superjet-100 |             58.6% |
| Boeing 737-300      |             61.7% |
| Boeing 777-300      |             65.9% |

The difference between aircraft types indicates that capacity utilization varies across the fleet and can be investigated further alongside route and operational factors.

---

## 💰 Revenue Analysis

The analysis covers approximately **₹21B in ticket revenue** across records with available ticket revenue.

Revenue was examined across:

* Aircraft types
* Routes
* Fare classes
* Occupancy
* Available seat capacity

The analysis focuses on revenue patterns rather than profitability because the dataset does not contain the required cost information.

---

## 🪑 Occupancy & Unused Capacity

The analysis identifies route-aircraft combinations with potentially high unused capacity.

A simple opportunity rule was used to identify candidates for further investigation:

* At least **10 observed flights**
* Occupancy below the median occupancy for the relevant route dataset

These are **investigation candidates**, not confirmed business opportunities or guaranteed sources of additional profit.

---

## 📈 Revenue Sensitivity Scenario

A **10% occupancy improvement scenario** was used to understand the potential revenue sensitivity to higher seat utilization.

This scenario assumes:

* Revenue increases proportionally with occupancy
* Average yield remains unchanged
* Other factors remain constant

Therefore:

> **Revenue uplift is not automatically profit uplift.**

The scenario is intended as a simple sensitivity analysis rather than a profit forecast.

---

## ⚠️ Important Data Limitation

The dataset contains ticket and booking revenue, but it does **not** contain flight-level:

* Fuel costs
* Labour costs
* Taxes
* Maintenance costs
* Lease costs
* Financing costs

Therefore, this project can measure **occupancy and revenue**, but it cannot calculate true **profit per seat** or flight-level profitability.

### Occupancy Data Limitation

The full flight-level dataset contains **33,121 flights**, but boarding observations are available for only **11,518 flights**.

Flights without boarding observations were **not automatically treated as having zero passengers**, because the absence of a boarding record does not establish why the record is missing.

Therefore, occupancy analysis is based on flights with available boarding observations.

---

## 💡 Business Thinking

The project follows a simple EDA-to-business framework:

```text
Business Question
       ↓
Data Question
       ↓
Analysis
       ↓
Finding
       ↓
Business Meaning
       ↓
Possible Action
```

The objective is not to create as many charts as possible.

The objective is to use data to answer business questions and identify areas that the airline could investigate further.

---

## 📁 Project Structure

```text
Airline-Operations-Revenue-Analysis/
│
├── datasets/
│   ├── aircrafts_data.csv
│   ├── airports_data.csv
│   ├── boarding_passes.csv
│   ├── bookings.csv
│   ├── flights.csv
│   ├── seats.csv
│   └── tickets.csv
│
├── EDA.ipynb
│
├── flight_level_analysis.csv
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd Airline-Operations-Revenue-Analysis
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Open the notebook

```bash
jupyter notebook
```

Open:

```text
EDA.ipynb
```

---

## 📦 Requirements

```text
pandas
matplotlib
jupyter
```

---

## 📌 Project Takeaway

This project demonstrates a complete Python-based EDA workflow:

**Data understanding → Cleaning → Multi-table integration → KPI creation → EDA → Business interpretation → Opportunity identification**

The analysis focuses on **seat occupancy, unused capacity, and revenue patterns**, while clearly separating measurable findings from areas that require additional cost data before profitability can be evaluated.
