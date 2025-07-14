# 🚿 Home Assistant Blueprint – Shower Detection (Light + Water Usage, No Extra Sensors)

This Home Assistant automation blueprint detects when someone is **showering**, using only two simple inputs:

- A **bathroom light switch** (`switch` domain)
- A **water usage sensor** (typically from a P1 meter or smart water meter)

No need for any extra template sensors, statistics, or helpers — this blueprint is plug-and-play.

---

## ✅ What It Does

When the bathroom light turns on, the blueprint:

1. Saves the current water usage value.
2. Waits a short amount of time (default: 60 seconds).
3. Checks if water usage increased beyond a configurable threshold (default: 0.1 = 100 liters).
4. If true → turns on a switch (e.g. ventilation, notification trigger, etc).

---

## 💡 Use Cases

- Trigger bathroom **ventilation fan** only when actually showering.
- Send a **notification** ("Shower started").
- Start playing **music** or adjust lighting automatically.

---

## 📥 Inputs

| Input               | Description                                                |
|---------------------|------------------------------------------------------------|
| `bathroom_switch`   | The switch that controls your bathroom light               |
| `water_sensor`      | Sensor that shows cumulative water usage (e.g. liters/m³)  |
| `water_delta`       | Minimum increase to consider it a shower (e.g. `0.1`)      |
| `wait_time`         | Time to wait after light turns on before checking usage    |
| `shower_switch`     | The switch to turn on when a shower is detected            |

---

## 🧠 Requirements

- A smart bathroom light switch (or motion-activated light switch)
- A water meter integrated into Home Assistant (e.g., via a P1 reader or flow sensor)
- Water usage must be cumulative (i.e., always increasing total usage)

---

## 🛠️ How to Use

1. Go to **Home Assistant > Settings > Automations & Scenes > Blueprints**
2. Click **Import Blueprint**
3. Use the RAW link to this file (or paste it manually if downloaded)
4. Create a new automation using this blueprint
5. Fill in:
   - Your bathroom light switch
   - Your water usage sensor
   - A switch to activate (e.g. `switch.shower_detected`)

---

## 🧪 Example Configuration

- **Bathroom switch**: `switch.badkamer_schakelaar`
- **Water usage sensor**: `sensor.p1water_watergebruik`
- **Shower trigger switch**: `switch.shower_detected`
- **Threshold**: `0.1` (i.e., 100 liters)
- **Wait time**: `60 seconds`

---

## 🙋 Support

Have questions or ideas? Feel free to open an issue or a pull request!
