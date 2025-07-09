# 🧹 Roomba Random Walk Simulation (MIT 6.0002)
This project simulates a robot vacuum (Roomba) navigating and cleaning a rectangular room. It's part of the problem set from MIT 6.0002: *Introduction to Computational Thinking and Data Science.*

The simulation models: 
* A robot moving randomly through space
* Dirt-covered tiles that are cleaned over time
* Core object-oriented design principles with abstract base classes

## 🧠 Core Classes Implemented

### ✅ `RectangularRoom` (Abstract Class)
Represents a grid of tiles, each with a configurable dirt level.

**Key features:**
- Tracks dirt levels per tile
- Allows cleaning with capped or partial capacity
- Checks if a position is inside the room

### ✅ `Robot` (Abstract Class)
Represents a cleaning robot with:
- Position, direction, speed, and cleaning capacity
- Methods to get/set state
- Designed to be extended by movement strategy subclasses

---

## 🔧 Implemented Methods So Far

- `clean_tile_at_position`
- `get_dirt_amount`
- `get_num_cleaned_tiles`
- `is_tile_cleaned`
- `is_position_in_room`
- `get_robot_position`, `set_robot_position`
- `get_robot_direction`, `set_robot_direction`

These methods form the foundation for simulating robot cleaning behavior.

---

## 🧱 Data Structures

- The room is backed by a dictionary: `{(m, n): dirt_amount}`
- Floating-point positions are mapped to tiles using `int(x), int(y)`
- Dirt is non-negative and clipped when cleaned beyond available amount

---

## 🚧 Next Steps (To Be Implemented)

- `StandardRobot` and `FaultyRobot` subclasses for movement behavior
- `EmptyRoom` and `FurnishedRoom` subclasses to explore obstacles
- Simulation runner to track efficiency and performance over time
- Visualization and analysis of cleaning patterns

---

## 🛠️ Skills Used

- Object-Oriented Programming (OOP)
- Abstract class design
- Floating-point vs grid-based coordinate mapping
- Randomized simulation setup
- Data structure design (dict-based tile tracking)
- Methodical debugging and testing
- Git/GitHub version control and documentation

---

## 📚 Course Reference

This project is part of [MIT 6.0002 – Introduction to Computational Thinking and Data Science](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-0002-introduction-to-computational-thinking-and-data-science-fall-2016/)

---

## 🧠 Personal Note

This project gave me a chance to explore simulation design using OOP. Instead of jumping straight to implementation, I practiced architectural thinking—especially how data and behavior interact in layered systems. I paid close attention to floating-point precision, dictionary-based grid tracking, and how abstract classes enforce structure while allowing flexibility.

This is part of my broader summer goal to deepen my algorithmic thinking, system design, and preparation for machine learning and cancer bioinformatics work.
