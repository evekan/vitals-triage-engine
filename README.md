# 🏥 Vitals Triage Engine

> A simple clinical logic engine built in Python to classify patients based on temperature, heart rate, and blood pressure.

Built for nurses, analysts, and healthcare quality professionals who want to explore Python-based automation and triage logic in real-world settings.

---

## 🔧 How It Works

This Python script defines a `triage()` function that accepts a patient's vital signs:

- Temperature (°F)
- Heart Rate (bpm)
- Blood Pressure (systolic/diastolic)

The function returns a triage status string based on clinically relevant rules:

```python
def triage(temp, hr, bp):
    if temp > 102 or hr > 120:
        return "Critical: Send to ER"
    elif temp > 99.5 or hr > 100:
        return "Moderate: Notify nurse"
    elif bp[0] < 90:
        return "Low BP: Schedule checkup"
    else:
        return "Stable"
patients = [
    {"name": "Alice", "temp": 101.5, "hr": 95, "bp": (110, 70)},
    {"name": "Bob", "temp": 103.2, "hr": 130, "bp": (118, 80)},
    {"name": "Carlos", "temp": 98.6, "hr": 80, "bp": (88, 60)}
]

for p in patients:
    result = triage(p["temp"], p["hr"], p["bp"])
    print(f"{p['name']} → {result}")
🧠 Features
Rule-based triage logic using if/elif/else

Processes patient vital signs from structured data

Categorizes urgency levels: Critical, Moderate, Low BP, or Stable

Built with beginner-friendly Python for automation and QA teams
Alice → Moderate: Notify nurse
Bob → Critical: Send to ER
Carlos → Low BP: Schedule checkup
Interpretation
Alice has mildly elevated vitals → notify nurse

Bob is in a critical state → ER referral

Carlos has low BP → checkup recommended
💼 Real-World Use Case
This script simulates logic that could be embedded in:

A hospital’s internal EHR rules engine

A Python backend script for triage alerts

A Power BI or Tableau dataflow logic layer

An automated workflow using Zapier, Alteryx, or FHIR pipelines
🚀 Future Expansion
Accept vitals from .csv or .json input

Return full structured output with urgency + alert type

Connect to FHIR API for real patient integration

Add machine learning risk scoring via Scikit-learn

Automate escalation messages via email or webhook
👩‍⚕️ Author
Eve Kandiyoti, DHA, RN
Healthcare Quality Analytics · Process Improvement · Data-Driven Nursing Leader

