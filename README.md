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
