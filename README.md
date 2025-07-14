# 🏥 Vitals Triage Engine

> A simple clinical logic engine built in Python to classify patients based on temperature, heart rate, and blood pressure.

Built for nurses, analysts, and healthcare quality professionals who want to explore Python-based automation and triage logic in real-world settings.

---

## 🔧 How It Works

This Python script defines a `triage()` function that accepts a patient's vital signs:

- Temperature (°F)
- Heart Rate (bpm)
- Blood Pressure (systolic/diastolic)

The function returns a triage status string based on clinically relevant rules.

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


---

## 👩‍⚕️ Author

Your name, role, and focus (e.g., “Registered Nurse focused on healthcare quality analytics and AI automation”)

