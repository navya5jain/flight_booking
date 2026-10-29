# SkyVoyage - Online Flight Booking System (Full-Stack College Project)

Ye project **HTML5, CSS3, JavaScript (Frontend)**, **Python Flask (Backend)**, aur **SQLite / PostgreSQL (Database)** par bana ek complete Full-Stack Flight Reservation System hai. Iske har code file mein **Hinglish comments** likhe gaye hain taaki aap har line ka matlab samajh sakein aur Viva mein aasani se explain kar sakein.

---

## 📂 Project Directory Structure

```text
skyvoyage_project/
│
├── app.py                  # Flask Backend Server & REST APIs (with Hinglish comments)
├── models.py               # SQLAlchemy Database Tables: Flight, Booking, Passenger
├── seed_data.py            # Initial domestic flights database seeder
├── requirements.txt        # Required Python libraries list
├── .env.example            # Database connection configuration example
├── .gitignore              # Git version control ignore rules
├── README.md               # Step-by-Step Setup & Viva Guide
│
├── templates/
│   └── index.html          # Main Frontend UI (Search, Seat Map, Boarding Pass)
│
└── static/
    ├── css/
    │   └── style.css       # Responsive CSS Styling & Print Media Queries
    └── js/
        └── app.js          # Frontend Fetch API Logic & Interactive Seat Selection
```

---

## 🚀 Step-by-Step: Apne Laptop Par Kaise Run Karein

### Step 1: Zip File Extract Karein
Zip file ko extract karein aur VS Code ya Terminal mein `skyvoyage_project` folder kholein:
```bash
cd skyvoyage_project
```

### Step 2: Virtual Environment Banayein aur Activate Karein
* **Windows (Command Prompt / PowerShell):**
  ```cmd
  python -m venv venv
  venv\Scripts\activate
  ```
* **Mac / Linux:**
  ```bash
  python3 -m venv venv
  source venv/bin/activate
  ```

### Step 3: Libraries Install Karein
```bash
pip install -r requirements.txt
```

### Step 4: Server Start Karein
```bash
python app.py
```
Ab browser khol kar **`http://127.0.0.1:5000`** par jayein!

---

## 🎓 Top Viva Questions & Answers (Examiner ke liye)

1. **Q: Humne `models.py` mein SQLAlchemy ORM kyu use kiya?**
   * **Ans:** SQLAlchemy ORM Python classes ko SQL tables mein convert karta hai. Isse humein SQLite se PostgreSQL par jane ke liye code nahi badalna padta, sirf `DATABASE_URL` badalna hota hai.
2. **Q: Ek hi seat do log book na kar lein, ye kaise roka gaya hai?**
   * **Ans:** `app.py` ke `POST /api/book` route mein hum database check karte hain ki us `flight_id`, `travel_date`, aur `seat_number` par pehle se koi `CONFIRMED` booking toh nahi hai. Agar hai, toh server `HTTP 409 Conflict` return kar deta hai.
3. **Q: Frontend aur Backend aapas mein kaise baat karte hain?**
   * **Ans:** `static/js/app.js` mein JavaScript `fetch()` API ke zariye HTTP GET, POST, aur DELETE requests bhejta hai, aur Flask backend JSON format mein data wapas bhejta hai.
