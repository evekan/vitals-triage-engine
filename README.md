# vitals-triage-engine
# 🏥 Vitals Triage Engine

A simple healthcare logic engine built in Python to classify patients based on temperature, heart rate, and blood pressure.

## 📋 Features

- Rule-based decision tree logic
- Returns triage category and alert level
- Designed to simulate real EHR signal processing
- Built for use in dashboards, automation, or FHIR pipelines

## 🔧 How It Works

```python
def triage(temp, hr, bp):
    if temp > 102 or hr > 120:
        return \"Critical: Send to ER\"
    elif temp > 99.5 or hr > 100:
        return \"Moderate: Notify nurse\"
    elif bp[0] < 90:
        return \"Low BP: Schedule checkup\"
    else:
        return \"Stable\"
patients = [
    {\"name\": \"Alice\", \"temp\": 101.5, \"hr\": 95, \"bp\": (110, 70)},
    {\"name\": \"Bob\", \"temp\": 103.2, \"hr\": 130, \"bp\": (118, 80)},
]
Alice → Moderate: Notify nurse
Bob → Critical: Send to ER
Carlos → Low BP: Schedule checkup
return {
    "urgency": "Critical",
    "action": "Send to ER",
    "notify": "pager"
}
import json

results = []
for p in patients:
    result = triage(p["temp"], p["hr"], p["bp"])
    results.append({"name": p["name"], "result": result})

with open("triage_results.json", "w") as f:
    json.dump(results, f, indent=2)
## 🧠 Features

- Rule-based triage logic
- Processes patient vital signs (temperature, heart rate, BP)
- Categorizes urgency levels: Critical, Moderate, Low BP, Stable
- Designed for nurses, analysts, and quality improvement use cases
## 🧪 Sample Output

**Interpretation**:
- Alice has slightly elevated vitals — nurse should be notified.
- Bob meets critical thresholds — send to ER immediately.
- Carlos is stable, but BP is low — follow-up needed.
## 💼 Real-World Use Case

This engine could be embedded in:
- A hospital EHR system to flag vitals in real time
- A Python script that sends automated alerts via email or SMS
- A Power BI or Tableau dashboard backend logic step
## 🚀 Future Expansion

- Accept vitals from a CSV or EHR export
- Add patient history to triage logic
- Connect to FHIR API for real-world integration
- Add predictive scoring using a machine learning model


