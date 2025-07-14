# Vitals Triage Engine 🏥

A simple clinical logic engine built in Python to classify patients based on temperature, heart rate, and blood pressure.

Built for nurses, analysts, and healthcare quality professionals who want to explore Python-based automation and triage logic in real-world settings.
## 🔧 How It Works

This Python script defines a `triage()` function that accepts a patient's vital signs:

- Temperature (°F)
- Heart Rate (bpm)
- Blood Pressure (systolic/diastolic)

It returns a triage result based on basic clinical rules:

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

---

### 🧠 Features

```markdown
## 🧠 Features

- Rule-based triage logic using `if/elif/else`
- Accepts patient vital signs as input
- Outputs clinical action recommendations
- Designed for beginner Python users in healthcare
## 🧪 Sample Output

### Interpretation

- Alice has mildly elevated vitals → notify nurse  
- Bob is in a critical state → ER referral  
- Carlos has low BP → checkup recommended
## 💼 Real-World Use Cases

This triage script can be adapted for multiple healthcare scenarios:

- 🔔 Embedded in an EHR system to trigger nurse call alerts based on vitals
- 📊 Used as a logic layer in Power BI to highlight unstable patients in dashboards
- 🔄 Included in an Alteryx workflow to classify patient risk from a CSV export
- 🤖 Combined with Zapier to send an email or SMS when a critical condition is detected
- 📁 Built into a command-line tool to clean and assess patient vitals from de-identified datasets
## 🚀 Future Improvements

- Accept vitals from `.csv` or `.json` input  
- Return full structured output (e.g., JSON)  
- Connect to FHIR API for real-world data  
- Add predictive scoring via scikit-learn  
- Automate escalation messages via email or webhook
## 👩‍⚕️ Author

**Eve Kandiyoti, DHA, RN**  
Healthcare Quality Analytics · Data-Driven Process Improvement Leader

