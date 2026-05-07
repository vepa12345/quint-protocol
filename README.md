# QUINT v4.1 (Hydra-Integrated)

**QUINT** is a fault-tolerant tactical communication protocol designed for high-interference (EW), zero-visibility, or silence-only environments.

## 1. Core Concept & License
* **Purpose**: Reliable data transmission via visual, binary, and tactile layers.
* **License**: MIT.
* **Resilience Rule**: The "One Dash" Rule — if transmission is interrupted, the receiver must assume a value of "1" (Highest danger/involvement).

## 2. Core Matrix (Five Nodes)
The protocol uses five markers (nodes), each with three levels of intensity.

| Node (Marker) | Value 1 ( - ) | Value 2 ( -- ) | Value 3 ( --- ) |
| :--- | :--- | :--- | :--- |
| **N1: STATUS** | CONTACT (Combat) | ALARM (Alert) | STILL (Silence) |
| **N2: RANGE** | CLOSE (0-30m) | THROW (Distance) | FAR (Long Range) |
| **N3: THREAT** | GUN (Firearm) | KNIFE (Melee) | FIRE / BOOM |
| **N4: LEVEL** | INVOLVED (Engaged) | DETECTED (Visual) | WATCHING (Observation) |
| **N5: EYES** | FRONT | SIDE (Flank) | BACK (Rear) |

## 3. Transport Layers

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
* **Height (Node):** Shoulder (N1), Collarbone (N2), Chest (N3), Solar Plexus (N4), Stomach (N5).
* **Impulse (Value):** Number of strikes in the chosen zone.

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
