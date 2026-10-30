# ✈️ SkyVoyage Pro v2 — Intelligent Flight, Lounge & Airport Cab Reservation System

**SkyVoyage Pro v2** is a full-stack web engineering college project built with **HTML5, CSS3, Vanilla JavaScript (ES6+)** on the frontend and **Python Flask + SQLAlchemy ORM (SQLite & PostgreSQL)** on the backend. It goes beyond basic ticket booking by combining **real Indian domestic airline schedules**, an **AI Fare Predictor & 7-Day Price Graph**, **Multi-Passenger Group Seat Selection**, **Landing-Synced Airport Cabs**, **Smart VIP Lounge Recommendations**, **Live Destination Weather & Packing Advisories**, and the **SkyBot AI Travel Assistant Chatbot**.

---

## 🌟 Key Features of SkyVoyage Pro v2

### 1. 🛫 Real Indian Domestic Airline Schedules & Fares
* Includes 21+ real domestic flights across **Bengaluru (`BLR`)**, **New Delhi (`DEL`)**, **Mumbai (`BOM`)**, **Goa (`GOI`/`GOX`)**, **Hyderabad (`HYD`)**, **Kolkata (`CCU`)**, **Chennai (`MAA`)**, and **Jaipur (`JAI`)**.
* Displays authentic airline codes and flight numbers (**IndiGo `6E-204`**, **Air India `AI-804`**, **Akasa Air `QP-1304`**, **Air India Express `IX-2742`**, **SpiceJet `SG-8710`**), aircraft models (**Airbus A321neo**, **Boeing 737 MAX 8**, **Boeing 787 Dreamliner**), terminal details, and real INR fare structures.
* Supports live filtering by **Max Price Slider** and **Airlines**, plus 1-click sorting by **Cheapest**, **Fastest**, and **Earliest Departure**.

### 2. 📈 AI Fare Predictor & 7-Day Interactive Price Trend Box
* Analyzes historical Google Flights route pricing to display a **Buy Now vs. Wait Recommendation Badge** with a confidence score (e.g., *89% Confidence • Fly Nov 8–10 to save ₹3,145* or *96% Confidence • Book Immediately before Goa surge*).
* Shows the **Google Flights Fair Price Band**, **Best Booking Window**, and an interactive **7-Day Price Bar Graph** where clicking any date bar automatically switches the travel date and reloads flights.
* Includes a live **Track Price Drop Alert** toggle for route monitoring.

### 3. 👨‍👩‍👧‍👦 Multi-Passenger Group Booking & Multi-Seat Aircraft Map (1 to 4 Travelers)
* Travelers can select **1 to 4 Passengers** in the search bar, and flight cards dynamically display both the **per-person fare** and the **group total**.
* The interactive **42-seat aircraft cabin map** (`7 rows × 6 columns: A, B, C | Aisle | D, E, F`) allows selecting multiple seats (`e.g., 3A, 3B, 3C`) with real-time seat conflict prevention (`HTTP 409 Conflict` if already taken).
* Dynamically generates individual passenger input cards (**Passenger 1 to Passenger N**) and maps each traveler to their specific chosen seat in the database (`1 Booking → Multiple Passenger rows`).

### 4. 🚕 Landing-Time Synced Airport Cab Pre-Booking
* Automatically reads the selected flight's exact **Arrival Time** (e.g., `09:05`) and schedules the airport pickup cab for **`Arrival Time + 20 mins` (`09:25`)** to account for runway taxi and baggage claim.
* Offers 4 transfer options: **No Cab (`₹0`)**, **Mini Hatchback (`+₹499`)**, **BluSmart Electric Sedan (`+₹749` • Zero Surge Guarantee)**, and **Prime SUV Innova Crysta (`+₹1,199` • Ideal for 4+ passengers)**.
* Embeds a **Confirmed Airport Cab Voucher** with pickup time, arrival gate pillar, and a **4-digit Driver OTP (`PIN: 4829`)** directly onto the Boarding Pass.

### 5. 🍽️ Smart Layover & VIP Terminal Lounge Pass Recommender
* Inspects the flight's departure hour and automatically recommends a discounted **Terminal VIP Lounge & Hot Buffet Pass (`+₹299/traveler`, 78% off the ₹1,400 walk-in rate)** for early-morning departures (before `09:00 AM`) and evening dinner flights (`06:00 PM+`).
* Scales the lounge fee automatically by the number of travelers (`₹299 × N Passengers`) and prints a **VIP Lounge Access Voucher** on the Boarding Pass.

### 6. 🌤️ Live Destination Weather & Packing Advisory
* Displays real-time meteorological conditions, temperature, and a tailored **Packing Tip** for the destination city both in the Route Intelligence Dashboard and on the printable **Electronic Boarding Pass** (e.g., *🌤️ New Delhi: 22°C Pleasant — Carry a light jacket for cool mornings & evenings* or *🌴 Goa: 31°C Sunny — Pack resort wear, sunglasses & SPF 50 sunscreen*).

### 7. 🤖 SkyBot AI Travel Assistant Chatbot
* Floating bottom-right conversational assistant supporting both **English and Hinglish** queries (e.g., *"sasti flight konsi hai?"*, *"weather & packing tip"*, *"how to book for multiple people?"*, *"VIP lounge pass"*, *"airport cab rates"*).
* Includes 1-click quick prompt chips and reads live route data to give instant, accurate answers.

### 8. 🎫 Printable Electronic Boarding Pass & PNR Management
* Generates a unique 6-digit PNR (`SV-XXXXXX`), itemizes the complete fare breakdown (**Base Fare + 12% Aviation GST + Seat Fees + VIP Lounge Pass + Airport Cab**), and formats a print-ready A4/PDF Boarding Pass via `@media print` CSS rules.
* Allows viewing and 1-click cancellation of bookings in the **My Bookings** tab, immediately releasing cancelled seats back into aircraft inventory.

---

## 🛠️ Technology Stack

| Layer | Technology Used | Purpose in Project |
| :--- | :--- | :--- |
| **Frontend Structure** | Semantic HTML5 (`index.html`) | Single-Page Application (SPA) views, modals, seat grid, boarding pass |
| **Styling & Layout** | Custom CSS3 (`style.css`) | CSS Variables, Flexbox, Grid, responsive breakpoints, `@media print` layout |
| **Client-Side Logic** | Vanilla JavaScript ES6+ (`app.js`) | Async `fetch()` API calls, multi-seat state engine, fare calculator, SkyBot AI |
| **Backend Framework** | Python 3 & Flask (`app.py`) | RESTful API endpoints, PNR generation, seat locking, fare & tax calculation |
| **Database & ORM** | SQLAlchemy ORM (`models.py`) | Relational schema compatible with both **SQLite** (local) and **PostgreSQL** (production) |
| **Version Control** | Git & GitHub (`.gitignore`) | Source code tracking, commit history, and GitHub Pages live deployment |

---

## 📂 Project Directory Structure

```text
skyvoyage_project/
│
├── app.py                              # Flask Backend Server & 7 RESTful API Endpoints (Port 5050)
├── models.py                           # SQLAlchemy ORM Database Schema (Flight, Booking, Passenger)
├── seed_data.py                        # 21+ Real Indian Domestic Flights Seeder Script
├── requirements.txt                    # Python Package Dependencies
├── .env.example                        # Environment Variables Template (SQLite & PostgreSQL)
├── .gitignore                          # Git Ignore Rules for venv, __pycache__, and .db files
├── start_website.command               # 1-Click macOS Terminal Launcher Script
├── SkyVoyage_Instant_Preview.html      # Standalone 1-Click Browser Preview File
├── README.md                           # Complete Project Documentation & Viva Guide
│
├── templates/
│   └── index.html                      # Main Frontend UI (Search, Predictor, Modals, Chatbot)
│
└── static/
    ├── css/
    │   └── style.css                   # Responsive Stylesheet & Print Media Rules
    └── js/
        └── app.js                      # Frontend State, Multi-Seat Engine, Predictor & Chatbot
```

---

## 🗄️ Relational Database Schema (`models.py`)

1. **`flights` Table (`Flight` Model)**:
   * `id` (Primary Key), `flight_number` (Unique), `airline`, `airline_code`, `aircraft`, `origin`, `origin_name`, `destination`, `destination_name`, `depart_time`, `arrival_time`, `duration`, `stops`, `stop_count`, `base_price`, `total_seats`.
2. **`bookings` Table (`Booking` Model)**:
   * `id` (Primary Key), `pnr` (Unique 6-digit code), `flight_id` (Foreign Key $\rightarrow$ `flights.id`), `travel_date`, `travel_class`, `passenger_count`, `seat_number` (comma-separated seats, e.g., `3A, 3B`), `seat_fee`, `base_fare`, `tax_amount`, `lounge_included`, `lounge_fee`, `cab_type`, `cab_fee`, `cab_pickup_time`, `total_amount`, `status` (`CONFIRMED` / `CANCELLED`), `gate`, `terminal`, `created_at`.
3. **`passengers` Table (`Passenger` Model — 1-to-Many with `Booking`)**:
   * `id` (Primary Key), `booking_id` (Foreign Key $\rightarrow$ `bookings.id`), `full_name`, `age`, `gender`, `seat_assigned`, `email`, `phone`.

---

## 📡 RESTful API Endpoints (`app.py`)

| HTTP Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/` | Renders the main web application (`templates/index.html`) |
| `GET` | `/api/flights` | Searches flights by `origin`, `destination`, `max_price`, and `sort` (`price`, `duration`, `depart`) |
| `GET` | `/api/predict` | Returns AI Fare Prediction, 7-day price curve, and Destination Weather & Packing Advisory |
| `GET` | `/api/flights/<id>/seats` | Returns all occupied seats for a specific flight and travel date |
| `POST` | `/api/book` | Validates seat availability, creates multi-passenger booking + lounge + cab records, returns PNR |
| `GET` | `/api/bookings` | Lists all bookings ordered by newest first |
| `DELETE` | `/api/bookings/<pnr>` | Cancels a booking by PNR and releases all assigned seats back into inventory |
| `POST` | `/api/chat` | Processes natural language queries for the **SkyBot AI Travel Assistant** |

---

## 🚀 How to Run Locally on Your Laptop

### Option A: Instant 1-Click Preview (Zero Terminal Required)
Double-click **`SkyVoyage_Instant_Preview.html`** (or `index.html` inside the live deploy folder) to open the complete interactive application directly in Chrome or Safari.

### Option B: Full-Stack Python Flask + SQL Server
1. Open Terminal inside the project directory:
   ```bash
   cd skyvoyage_project
   ```
2. Create and activate a Python virtual environment:
   * **macOS / Linux:**
     ```bash
     python3 -m venv venv
     source venv/bin/activate
     ```
   * **Windows:**
     ```cmd
     python -m venv venv
     venv\Scripts\activate
     ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Start the Flask server (runs on **Port 5050** by default to avoid macOS AirPlay Receiver conflicts on Port 5000):
   ```bash
   python3 app.py
   ```
5. Open **`http://127.0.0.1:5050`** in your browser.

---

## 🎓 Viva Voce Preparation Guide (Top Examiner Questions)

1. **Q: How did you implement Multi-Passenger booking in the database?**
   * **Ans:** "We designed a **1-to-Many relationship** between the `bookings` table and the `passengers` table using SQLAlchemy (`db.relationship('Passenger', backref='booking')`). A single `Booking` record stores the group PNR, total fare, and comma-separated seats (`3A, 3B`), while each traveler is stored as an individual row in the `passengers` table with their specific `seat_assigned`."
2. **Q: How does the Landing-Synced Airport Cab feature work?**
   * **Ans:** "When a user selects a flight, our JavaScript helper `calculateCabPickupTime()` parses the flight's 24-hour `arrivalTime` (e.g., `09:05`), adds a 20-minute buffer for runway taxi and baggage claim (`09:25`), and stores the selected vehicle (`Mini Hatch`, `BluSmart EV`, or `Innova SUV`), pickup time, and fare directly in the booking record."
3. **Q: How does the Smart Lounge Recommender decide what to show?**
   * **Ans:** "It inspects the departure hour of the chosen flight. If the flight departs before `09:00 AM` or after `06:00 PM`, it dynamically customizes the recommendation banner for breakfast or dinner buffet access at `₹299/traveler` and multiplies the fee by the group size."
4. **Q: Why use SQLAlchemy ORM instead of raw SQL queries?**
   * **Ans:** "SQLAlchemy abstracts the database engine so the exact same Python models run seamlessly on **SQLite** (`sqlite:///skyvoyage_v2.db`) for local development and **PostgreSQL** (`postgresql://...`) in production just by changing the `DATABASE_URL` environment variable, while also preventing SQL injection."
