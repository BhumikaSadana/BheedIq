# 🚨 BheedIQ

**Bheed ko samjho, haadsa se pehle.**
*Understand the crowd, before the disaster.*

BheedIQ predicts crowd crushes **10-15 minutes before they happen** and guides people to safety. It runs on a live crowd simulator, so there is nothing to install: open it in a browser and it works.

### 🔗 [Live Demo](https://bheediq.vercel.app/)

---

## 💡 The Problem

Stampedes don't start suddenly. They build: density rises, movement slows, people start to push. By the time anyone reacts, it is usually too late. BheedIQ spots the build-up early, using signals that phones already carry, with no extra hardware or cameras.

## ✨ Features

| Feature | What it does |
|---|---|
| 🎬 **Crowd Story Landing** | A scroll-driven animation of walking crowds: calm, building, critical, then BheedIQ re-routes them. Dots even part around your cursor. |
| 🗺️ **Live Lehar Map** | A heatmap of 12 venue zones with flowing crowd particles. Zones "breathe" faster as risk rises. Click any zone for density, flow speed, turbulence and trend. |
| ⏱️ **Crush Forecast** | Per-zone countdown ("Gate 3 critical in 08:12") with confidence %, sparkline and plain-language drivers. |
| 🔮 **Forecast Slider** | Drag Now → +5 → +10 → +15 min and watch the map repaint with predicted risk. |
| ↪️ **Auto Reroute** | Dijkstra pathfinding over the zone graph ranks 3 routes (Fastest / Safest / Balanced). Apply one and risk actually drops in the simulation. Undo supported. |
| 📢 **PA and LED Scripts** | Auto-generated announcements in **English and Hindi**, with copy buttons and an animated LED signage preview. |
| 🚑 **Dispatch** | One-tap Medical / Police / Volunteer units with live status (Queued → Sent → On the way → Arrived → Resolved). Arrival eases crowd pressure. |
| 📱 **Attendee Mode** | Anonymous, consent-first phone view: one big arrow, one calm sentence ("Head to Exit B · 40 sec"), Hindi/English, large text, voice readout and a **hold-to-send SOS** that creates a live dispatch. |
| 🎛️ **Scenarios** | Normal Evening, Festival Peak, Gate Rush and Panic Trigger, with pause and 1x/2x/4x speed. |

## 🧠 How the risk score works

```
Risk = 100 × (0.45 × density + 0.25 × (1 − flow speed) + 0.30 × turbulence)
```

- Smoothed over time, with a linear trend fitted over the last 60 seconds.
- **Time-to-critical** = (85 − risk) / slope.
- Interventions (reroute, dispatch arrival) change the simulated flow, so their effects are real and visible in the numbers.
- A seeded random generator keeps the demo deterministic.

## 🛠️ Tech

Pure **HTML + CSS + JavaScript** in a single file. HTML Canvas for the crowd and map rendering. No frameworks, no build step, no backend.

## ▶️ Run locally

```bash
git clone https://github.com/BhumikaSadana/BheedIq.git
cd BheedIq
# open index.html in your browser (or use VS Code Live Server)
```

## 🎮 Quick demo (60 seconds)

1. Open the live demo and scroll through the crowd story.
2. Click **Simulate Festival**.
3. Watch Gate 3 climb toward critical in the **Crush Forecast** strip.
4. Click the red zone, then **Reroute → Apply reroute** and watch risk fall.
5. Hit **+ Medical** to dispatch a unit.
6. Open **Attendee** and drag the "you are here" dot to see live guidance.

## 🔒 Privacy by design

Attendees stay anonymous: no name, no phone number, only motion and zone data.

## 🚀 Future scope

- Real phone sensor input (accelerometer jitter and location pulses)
- Backend with WebSockets for live multi-device sync
- Ripple Lab: panic-wave rehearsal before an event
- Venue editor and ML-based forecasting

---

Built for a public safety and emergency response hackathon. 🇮🇳
