# QUINT v 5.0 (Multilayer Protocol)

**QUINT** is a fault-tolerant communication protocol designed to **save lives** in extreme environments: high interference, zero visibility, silent operations, or total radio failure.

## Purpose
The protocol is engineered for emergency services (paramedics, firefighters, rescue teams) as a vital tool for transmitting critical information in disaster zones, under rubble, or during industrial catastrophes where every second counts.

## Key Principles
* **Reliability:** Data transmission through visual, binary, and tactile layers.
* **Survivability:** The "Single Dash Rule" — if transmission is interrupted, the receiving party must default to Value "1" (maximum danger/engagement priority).
* **Precision:** Triple Redundancy — a data packet is considered valid if 2 out of 3 iterations match.
* **Adaptability:** A system of departmental headers modifies the context of the message based on the service (Medical, Fire, Police).

## 1. Concept and Licensing
* **Objective:** Robust data transmission via visual, binary, and tactile layers.
* **License:** MIT.
* **Survivability Rule:** "Single Dash Rule" — in case of interruption, the receiver assumes Value "1" (maximum threat/involvement).

## 2. Base Matrix (5 Nodes)
The system utilizes 5 zones (markers) or pulses. Each category features 3 intensity levels.

| Node (Zone) | Value 1 | Value 2 | Value 3 |
|:---|:---|:---|:---|
| **PULSE** | `-` | `--` | `---` |
| **N1: STATUS** `.` | ACTIVE (On-site) | ALARM (Alert) | STANDBY |
| **N2: DISTANCE** `..` | CLOSE (0-30m) | MEDIUM | FAR |
| **N3: THREAT** `...` | ASSISTANCE NEEDED | TRAUMA | EXPLOSION / FIRE |
| **N4: LEVEL** `....` | ENGAGED | DETECTED | OBSERVING |
| **N5: SECTOR** `.....` | FRONT | FLANK | REAR |

## 3. Transport Layers
1. **PULSE-QUINT (Binary):** Transmission via light, sound, vibration, or pressure (using dots and dashes).
2. **VIS-QUINT (Tactile):** Transmission via physical contact on specific body zones: Head (N1), Shoulder (N2), Chest (N3), Stomach (N4), and Thigh (N5).

### PULSE-QUINT (Binary Layer)
Used for transmission via light, sound, vibration, or pressure.
* **Marker (Dot `.`):** A short, sharp impulse. The number of dots indicates the **Node number**.
* **Data (Dash `-`):** A distinctly long impulse (roughly 3x the duration of a dot). The number of dashes indicates the **Value**.
* **Rhythm Guidelines:**
* **Dot:** Instantaneous "tap".
* **Dash:** Sustained "hold".
* **Intra-node pause:** Short break (equal to one dot).
* **Inter-node pause:** Long break (clear silence to separate the category from the data).
* **Example:** `.. ---` (Node 2, Value 3) = **RANGE: FAR**

### VIS-QUINT (Visual/Tactile Layer)
Transmission via palm strikes to the chest.
* **Height (Node):** Head / Helmet (N1), Shoulder (N2), Chest (N3), Stomach / Belt (N4), Thigh (N5).
* **Impulse (Value):** Number of strikes in the chosen zone. Also it is allowed to show by fingers, only if the visibility clear.

## 4. Operational Rules
* **Triple Redundancy**: Every packet is transmitted three times. A packet is valid if 2 out of 3 iterations match.
* **Hierarchy**: Binary Pulse (Math) > Gestures (Motor skills) > Voice.
* **Priority Zero**: The **CANCEL** command immediately resets the current session across all channels.

## 5. Commands & Headers
* **CANCEL**: `... ... ...` (Three blocks of three dots) or "X" arm gesture.
* **INTERRUPT**: 5+ rapid dots or hand-shake gesture.
* **COPY (Acknowledged)**: `.. .. ..` (Three blocks of two dots).
* **REPEAT**: `.... ....` (Two blocks of four dots).
* **AGENCY HEADERS**: Optional prefixes (Police, Medic, Fire) to provide context.
* **Police:** `. .. ...` (1-2-3 sequence).
* **Medic:** `.. ... .` (2-3-1 sequence).
* **Firefighter:** `... . ..` (3-1-2 sequence).
* **SALAM (Greeting)**: Closed fist to heart. Non-tactical, used for psychological connection ("I'm okay / Good luck").

## 6. Stream Chaining & Overlay
To describe complex situations, the protocol uses a method of sequential attribute summation ("chaining").

* **Mechanism:** Nodes are transmitted one after another with a short pause between them.
* **Example:** To transmit "Firefight" (N1-V1) and "Medic needed" (Medic Header + N3-V1).
* **Overlay Logic:** If one zone (e.g., Threat N3) involves multiple factors like both a firearm and fire, the operator transmits Node N3 with Value 1, pauses, and then transmits Node N3 again with Value 3.

---
*QUINT: When words fail, communication continues.*
* **Stream Termination:** Any multi-layered transmission must end with the **COPY** signal (`.. .. ..`) so the receiver knows the sequence is complete.
