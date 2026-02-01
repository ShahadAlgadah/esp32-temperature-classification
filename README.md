#Patient Temperature Classification System  
(ESP32 + ILI9341 | Embedded Systems Project)



This project demonstrates how embedded systems can be used for real-time health monitoring and decision-based actuation.
It uses an ESP32 microcontroller and an ILI9341 TFT display to classify patient temperatures based on manual input via the Serial Monitor, 
presenting data visually in a color-coded table and activating LEDs accordingly.


---

🔹 Project Focus Areas:
- Embedded Systems
- IoT-based monitoring
- Human-centered system design

---

## 💡 Features

- Manual temperature input via **Serial Monitor**
- Automatically updates a table on the **TFT screen**
- Displays temperature readings and status (**OK** / **HIGH**)
- 🔴 **Red LED** turns ON if temperature > 35°C  
- 🟢 **Green LED** turns ON if temperature ≤ 35°C  
- Command `clear` resets the screen
- Display is rotated **horizontally** (landscape)

---

## 🖥️ Display Layout

| No. | Temp (°C) | Status |
|-----|-----------|--------|
| 1   | 36.4      | HIGH   |
| 2   | 34.7      | OK     |
| ... | ...       | ...    |

- Text is color-coded:
  - 🔴 Red for HIGH temperature (> 35°C)
  - 🟢 Green for OK temperature (≤ 35°C)
  - ⚫ Black for headers

---

## 🖼️ Project Output Example

This image shows the actual result of the system displaying temperatures on the TFT screen:

![Output Image](Output.png)

---

## 🔌 Components Used

- ESP32 Dev Board
- ILI9341 TFT Display (SPI interface)
- 2 LEDs (Red & Green) with 220Ω resistors
- Breadboard and jumper wires

---

## 📥 Serial Commands

| Command | Action                        |
|---------|-------------------------------|
| `36.5`  | Adds a new temperature entry  |
| `clear` | Resets the screen and table   |

---

## ⚙️ How It Works

1. User enters a temperature (e.g., `34.8`) in the Serial Monitor.
2. The system adds the temperature and its status to the table.
3. Based on the value, it turns on the **red** or **green** LED.
4. After 10 rows, the screen automatically resets.

---

## 🧠 Key Code Snippet

```cpp
if (temp > 35.0) {
  tft.setTextColor(ILI9341_RED);
  digitalWrite(LED_RED, HIGH);
  digitalWrite(LED_GREEN, LOW);
} else {
  tft.setTextColor(ILI9341_GREEN);
  digitalWrite(LED_RED, LOW);
  digitalWrite(LED_GREEN, HIGH);
}
```

## 🔗 Live Simulation (Wokwi)

You can try this project directly in the Wokwi simulator:

👉 [Open in Wokwi](https://wokwi.com/projects/435286436648704001)

---

## 👤 Author

**Shahad Algadah**  
GitHub:[GitHub](https://github.com/ShahadAlgadah)
LinkedIn:[LinkedIn](https://www.linkedin.com/in/shahad-algadah-841509337/)



