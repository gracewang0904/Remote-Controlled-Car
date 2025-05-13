# Remote-Controlled-Car 🚗

This repository documents the design and development process of a Remote-Controlled Car project. **Codebase is private. Please reach out if you'd like access**.

## 🧠 Project Overview

This RC car has the following components:
- A 20x20 environment
- A user-controlled car
- Two rectangular obstacles
- A tracking window tracking the movement of the car

What it can do:
- Car movement
- Brings the car to within the environment if it is out-of-bound
- Object tracking
- Position updates / crush feedback
- Object tracking


## 🔧 Technologies & Tools

C, Bash script

## 🏃:How to use it

Input commands to drive the car, track movement, and avoid obstacles in real-time.

Input Format:

- ✅ One command per line.
- ✅ Valid commands:
  - `D` – **Done** driving, ends the session.
  - `[DIRECTION] [DISTANCE]` – Drives in the given direction.
    - Directions: `N` = North, `S` = South, `E` = East, `W` = West  
    - Distance: Any integer within the MAX-TRAVEL-DISTANCE (positive, zero, or negative)

Examples:

- `N 3` → Move 3 units north (if possible)
- `E 8` → Move up to the max allowed distance east (e.g., capped at 5 if `MAX_TRAVEL_DISTANCE = 5`)
- `S -4` → Interpreted as moving 4 units north

Output Behavior:

🖨 **Always prints the car's position** after a drive command, even if no movement occurred
- 🚧 If movement is blocked by an obstacle:
- - Not moving: Obstacle in way.
- 🧱 If car tries to go outside the boundary:
- - A **crash is reported** and the session ends
- 🗺 If car moves outside the tracking window:
- - The tracking window is updated
