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

### ✅ `EmptyRoom` (Subclass of RectangularRoom)
A basic room with no obstacles.
- Overrides `get_num_tiles` using total `width x height`
- `is_position_valid` defers directly to `is_position_in_room`

### ✅ `FurnishedRoom` (Subclass of RectangularRoom)
A room that includes randomly placed furniture. 
- Furniture is stored as a list of tile coordinates
- `is_position_valid` is overridden to exclude furnished tiles.
- Implements furniture-safe random position generation
- Uses wrapper methods (`is_tile_furnished`, `is_position_furnished`) for clarity
  
---

## 🔧 Implemented Methods So Far

- `clean_tile_at_position`
- `get_dirt_amount`
- `get_num_cleaned_tiles`
- `is_tile_cleaned`
- `is_tile_furnished` (FurnishedRoom only)
- `is_position_furnished` (FurnishedRoom only)
- `is_position_in_room`
- `get_robot_position`, `set_robot_position`
- `get_robot_direction`, `set_robot_direction`
- `get_random_postion` (for both Empty and Furnished rooms)
- `get_num_tiles` (customized per subclass)

These methods form the foundation for simulating robot cleaning behavior across various environments, inclduing rooms with and without obstacles.

---

## 🧱 Data Structures

- The room is backed by a dictionary: `{(m, n): dirt_amount}`
- Furniture tiles are stored in a list: `[(x,y), ...]`
- Floating-point positions are mapped to tiles using `int(x), int(y)`
- Dirt is non-negative and clipped when cleaned beyond available amount

---

## 🔍 Design Insight: Abstract Classes

This project uses **abstract classes** (`RectangularRoom` and `Robot`) to enforce structure while allowing flexible implementation. Abstract classes define the essential methods and attributes all subclasses must have but leave specific behaviors—like how a robot moves or how a room is constructed—to be defined by subclasses.

This design pattern helped me:

* Focus on shared state and behavior while isolating differences
* Create reusable code scaffolding
* Understand how simulation components (like rooms and robots) can be extended for more complex behavior (e.g., furnished rooms, faulty robots)

By implementing the base logic in abstract classes and deferring custom behavior to subclasses, I practiced building systems that scale in complexity without becoming chaotic.

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
