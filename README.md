# Online UPS Power Board

Compact, always-on UPS to keep devices (modems, POS terminals, etc.) running during power outages. Features a **Adjustable output** and a simple, flexible design.

---

## ✨ Key Features

- 🔋 **Adjustibale Output** – Stable power for sensitive electronics  
- 🔌 **Online UPS** – Seamless switchover, zero downtime  
- 🔁 **Flexible Battery** – Single Li-ion cell (default) or multiple parallel cells (same voltage)  
- ⚡ **High-Current Ready** – Supports up to 2.5A (depending on regulator)  
- 🧱 **Castellated Edge Boost Module** – Easy soldering and robust integration  
- ⚙️ **Configurable Relay** – Coil can run from adapter (default) or 5V regulator (via solder bridges)

---

## 🔧 Hardware & Configuration

### Power Regulator
- Charger IC accepts **max 6V input**.  
- Modems/POS usually use **9–12V adapters** → a high-current regulator is included on board.

**Recommended**: Use our **TPS54302 buck module** ([repo link](https://github.com/tahanazeri1/TPS54302-Buck-StepDown.git)) for easy 3A output.  
**Alternative**: Linear regulator (e.g., LM78xx/L7805) **if** battery charge current is set to **≤ 200mA**.

### Boost Module (Castellated Edge)
- A separate **MT36xx-based boost module** ([repo link](https://github.com/tahanazeri1/MT36xx-Boost.git)) steps up battery voltage.  
- Castellated edges for reliable soldering and compact footprint.

### Relay Power (Solder Bridge Selectable)
| Mode | Solder Bridge 1 | Solder Bridge 2 | Relay Coil Source |
|------|----------------|----------------|-------------------|
| **Adapter Direct** (Default) | Closed | Open | Main adapter (9–12V) |
| **Regulated 5V** | Open | Closed | 5V regulator output |

### Battery
- Default: **Single Li-ion cell** (3.7V).  
- Optional: **Multiple parallel cells** (same voltage).  
- Configure charge current based on battery capacity and regulator capability.

---

## 📦 Getting Started

1. Assemble the board per the schematic.  
2. Connect battery (Li-ion cell or parallel pack). 
3. Connect input power (**9–12V adapter** ).  
4. Connect your load (modem, POS, etc.).  
5. Power on and enjoy uninterrupted operation!

---

## 🛠️ Customization Tips

- for Use linear regulator (e.g., L7805) → set charge current to **≤ 200mA**.  
- Use TPS54302 buck module → supports up to **3A** output. (Recomended) 
- Adjust relay solder bridges to choose coil power source.  
- The boost module's castellated edge design simplifies rework/replacement.
