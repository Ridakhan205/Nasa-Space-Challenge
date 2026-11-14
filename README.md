# 🚀 ASTRA: Return-to-Gravity Early Warning

**ASTRA** is a browser-based mission-control dashboard built for the NASA App Challenge. It explores how personalized cardiovascular trends (heart rate, HRV, blood pressure, SpO₂) could give astronauts and flight surgeons an early signal of **orthostatic intolerance (OI)** as a mission approaches return to Earth's gravity.

Everything runs locally in a single HTML file. No build step, no server, no account, and no data leaves your browser.

## Features

- **Crew Orbit Index**: live gauge of deviation from each crew member's own baseline.
- **Mission timeline**: scrub through simulated 30–90 day missions (Adaptation → Cruise → Pre-return → Return window).
- **Stand-test lab**: virtual stand-up test comparing the selected day's response with the baseline.
- **Personal AI baseline model**: train from your own CSV or the demo mission, and see the readings used, what the model learned, and its effect.
- **Live stream**: connect a WebSocket source or use the built-in demo stream.
- **Live ECG monitor**: animated synthetic ECG that follows the selected day's heart rate.
- **NASA resources**: links to the Human Research Roadmap and OSDR.

## Quick start

Open `index.html` in any modern browser.

## Training CSV

Columns: `hr`, `hrv`, `sbp`, `dbp`, `spo2` (at least two, 10+ rows). Names like `heart_rate`, `rmssd`, `systolic` and `diastolic` are recognised. Comma, semicolon or tab separators work.

## Live data format

Send JSON to a WebSocket (default `ws://localhost:8765`):

```json
{"hr": 68, "hrv": 52, "sbp": 118, "dbp": 78, "spo2": 98}
```

## Disclaimer

Telemetry is **synthetic demonstration data**, not NASA astronaut telemetry. The anomaly index is a relative deviation score, not an OI probability or medical diagnosis, and the model is not clinically validated.

## NASA resources

- [Human Research Roadmap: Cardiovascular risk](https://humanresearchroadmap.nasa.gov/Risks/risk.aspx?i=179)
- [NASA Open Science Data Repository (OSDR)](https://science.nasa.gov/biological-physical/data/osdr/)
- [OSDR Visualization Portal](https://visualization.osdr.nasa.gov/)

## License

MIT
