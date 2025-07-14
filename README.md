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


