# 🐦 Flappy Bird Clone - Python & Pygame

A modern recreation of the iconic mobile game, built with **Python** and **Pygame**. This project focuses on implementing smooth physics, state management, and Object-Oriented Programming (OOP) principles.

## 🚀 Inspiration & Goals

The goal of this project was to recreate the "casual game" that defined an era of mobile gaming. While the gameplay is simple (one action: jump), it hides interesting mathematical complexity.

* **Why this game?** It's the ideal project to demonstrate mastery of **Delta Time**, **vector physics**, and **state management** in Python.
* **Aesthetics:** The game stays true to the original pixel-art style but uses a modern resolution (**960 x 540**) for clarity on today's screens while maintaining that classic arcade feeling.

## 🛠️ Technical Architecture (OOP)

The project is built using **Object-Oriented Programming** to ensure clean and maintainable code:

1.  **Modularity:** Every element (Bird, Pipes, Menu) is a separate class inheriting from a `BaseObject`.
2.  **Menu Management:** A `MenuManager` handles transitions between the "HomeScreen" and active gameplay without unnecessary resource reloading.
3.  **Optimization:** Custom utilities like `load_image` use `.convert_alpha()` to optimize texture loading and transparency.



---

## 📂 Project Structure

### 1. Configuration & Resources (`config.py`)
Centralized settings to avoid "hardcoded" values:
* **Constants:** Resolution (960x540), FPS (60), and resource paths.
* **Utilities:** Implementation of a `clamp` function to keep the bird within screen bounds and optimized asset loading.

### 2. Object Logic (`objects.py`)
* **Player Class:** Implements movement physics using vertical velocity (`dy`) influenced by constant gravity. The bird's rotation angle is calculated dynamically based on its movement direction.
* **Pipe Class:** A system of obstacles generated with a gap. Collision detection uses `colliderect` with slightly reduced hitboxes to make the gameplay fair and "forgiving" for the player.

### 3. State Management (`menu.py`)
Controlled by a `MenuManager` to separate game screens:
* **HomeScreen:** Manages the idle state where the background and ground move at a constant speed to create depth.
* **Active Game Loop:** Calculates score, generates pipes, and progressively increases `original_speed` to raise difficulty.
* **Scoring System:** Scores are displayed using individual digit images to preserve the original retro font.

### 4. Execution & Synchronization (`main.py`)
The heart of the application:
* **Delta Time (dt):** Movement is normalized using `dt`. This ensures that the bird and pipes move at the same speed regardless of the CPU's processor speed.
* **Event Handling:** Constant monitoring for keyboard/mouse inputs and application exit events.

---

## 🔧 How to Run

1. Make sure you have **Python** and **Pygame** installed:
   ```bash
   pip install pygame
