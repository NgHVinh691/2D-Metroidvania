# 2D Metroidvania: Modular Exploration Framework
**A comprehensive Unity project showcasing advanced State Machine architecture and fluid combat systems.**

## 🎯 Overview
This project is a 2D Metroidvania exploration game developed over 3 months. It features a scalable code architecture designed to handle complex player movements, modular enemy AI, and a seamless world transition system.

## 🚀 Technical Highlights

### 1. Robust State Machine System (FSM)
The core of the game is built on a **Generic State Machine** pattern to ensure clean, decoupled logic:
* **Player FSM:** Manages 10+ states (Idle, Run, Jump, Fall, Attack, etc.) ensuring smooth transitions and responsive controls.
* **State-Driven Animations:** Animation triggers are handled directly within the FSM states, eliminating "Animator Transition Hell" and ensuring perfect sync between logic and visuals.

### 2. Advanced Combo & Combat Logic
* **Input Buffering:** Implemented using `StateMachineBehaviour` (`TransitionOneBehaviour.cs`) to allow "caching" of attack inputs. This creates a professional, fluid combo feel where the player can chain attacks seamlessly.
* **Decoupled Combat:** Utilized the `IDamageable` interface, allowing the combat system to remain flexible. Any entity (Boss, Enemy, or Destructible object) can receive damage without being tightly coupled to the attacker.

### 3. Modular Enemy AI
The project demonstrates a clear architectural evolution:
* **Evolutionary Design:** Transitioned from monolithic behaviors (`EnemyScript`) to a refined, state-based AI (`EnemyState`).
* **AI Behaviors:** Modular states for Patrolling, Chasing, Attacking, and Returning Home, making it easy to add new enemy types by reusing existing states.

### 4. World & Systems Management
* **Scene Management:** A custom `SceneEntranceManager` handles player spawning and data persistence when moving between interconnected world maps.
* **Performance Optimization:** Implemented **Object Pooling** for projectiles (Ranged Skeleton) to maintain high performance during intense combat.
* **Environmental Effects:** Custom Parallax scrolling and smooth camera dampening for an immersive experience.

## 📂 Key Scripts (Recommended for Review)
To see my coding style and logic, please check:
* `Assets/Scripts/TestState/PlayerController.cs`: The core player logic.
* `Assets/Scripts/EnemyState/`: Implementation of the FSM AI.
* `Assets/Scripts/TransitionOneBehaviour.cs`: Advanced combo buffering logic.
* `Assets/Scripts/IDamageable.cs`: Clean interface-based combat system.

## 🛠 Tech Stack
* **Engine:** Unity 2022.3+
* **Language:** C#
* **Patterns:** Finite State Machine (FSM), Singleton, Observer, Object Pooling, Interface-based Design.
