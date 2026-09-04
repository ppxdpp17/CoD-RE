# CoD-RE: Kosse Mine & Sawyer Ranch

A first-person survival shooter developed in **Unity** (C#) showcasing custom player locomotion, modular weapon mechanics, AI pathfinding across two distinct narrative environments, and two different game modes (horde or story). 

Developed as part of the *Game Development* course within the Master's in Informatics Engineering at Universidade de Trás-os-Montes e Alto Douro (UTAD).

> 📄 **Academic Documentation:** For a detailed breakdown of the development process, architecture, and post-mortem analysis, refer to the full [Technical Report (PDF)](docs/technical-report.pdf).


## 📸 In-Engine Showcase

| Sawyer Ranch (Night Atmosphere) | Kosse Mine Boss Encounter |
| :---: | :---: |
| ![Sawyer Ranch](docs/images/sawyer-ranch.png) | ![Boss Encounter](docs/images/boss-encounter.png) |

| First-Person Rig & Shotgun | AI NavMesh Surface & Companion Links |
| :---: | :---: |
| ![FPS Rig](docs/images/weapon-rig.png) | ![NavMesh Setup](docs/images/navmesh-setup.png) |

---

## 🎮 Game Modes & Scenarios

The project features two distinct game modes tied to independent environments and storylines:

### 1. Sawyer Ranch – Endless Horde Survival
* **Protagonist:** Michael Sawyer (Rookie Police Officer).
* **Core Objective:** Survive infinite waves of infected attacking the family ranch.
* **Mechanics:** Round-based spawn director, score-per-kill tracking, and timed recurring supply respawns (health and armor kits).

### 2. Kosse Mine – Tactical Extraction & Boss Encounter
* **Protagonist:** Leon Winters (Bioterrorism Security Veteran).
* **Core Objective:** Navigate underground tunnels and dungeon corridors to extract captured squad members.
* **Mechanics:** Non-linear exploration, key-item discovery gates, companion squad escort pathfinding, and an end-stage boss battle featuring a dedicated health UI.

---

## 🛠️ Technical Implementation & Architecture

### Custom Locomotion & Physics
* **First-Person Controller:** Built using Unity's `CharacterController` .
* **Locomotion Mechanics:** Smooth sprint acceleration, distance-based dash mechanics, double-jumping, variable gravity manipulation, and camera-offset crouch/prone stances.
* **Camera Look:** Decoupled mouse look with persistent runtime sensitivity scaling.

### Weapon Mechanics & State Machine
* **Ballistics:** Raycast-driven hitscan shooting with directional surface impact particles and muzzle flash VFX.
* **State Machine Recoil & Reload:** Multi-clip reload cycle handled through a dedicated `Animator Controller` to ensure seamless transitions between single-shell loading, idle states, and firing kickback.
* **Sights & Spread:** Dynamic crosshair with precision aiming down sights (ADS) field-of-view scaling.

### Artificial Intelligence & Pathfinding
* **Hostile AI:** Multi-tiered zombie profiles (fast flankers, heavy slow brutes, and a high-health boss) configured with dynamic player-tracking aggro radio and melee damage states.
* **Companion Escort AI:** Friendly squad NPCs (`Anthony Mark`, `Peter War`) driven by `NavMeshAgent`.
* **Discontinuous Geometry:** Integrated `NavMeshLink` transitions and custom `NavMeshSurface` rebaking to allow seamless companion traversal across fractured dungeon architecture.

### Systems & UI / UX
* **Damage Pipeline:** Segmented damage model where incoming attacks deplete protective armor integrity prior to health degradation.
* **Dual Minimap Cameras:** Orthographic top-down tracking cameras rendering custom billboard UI blips for points of interest, key objectives, and lights.
* **Objective Tracking:** Dynamic HUD checklist providing progressive stage feedback and interaction prompt popups.
* **Cutscene Engine:** Scripted in-engine camera tracks, custom audio mixers with voiceover tracks, timed subtitles, and screen fade controllers.

---

## ⌨️ Controls

| Action | Primary Key / Input |
| :--- | :--- |
| **Movement** | `W` / `A` / `S` / `D` |
| **Look** | Mouse Movement |
| **Shoot** | Left Mouse Button (`Mouse 1`) |
| **Aim Down Sights (ADS)** | Right Mouse Button (`Mouse 2`) |
| **Jump / Double Jump** | `Spacebar` |
| **Sprint** | `Left Shift` |
| **Dash** | Dedicated Movement Input |
| **Crouch / Prone** | `C` (Crouch) / `Z` (Prone) |
| **Interact / Open Doors** | `E` |
| **Pause Game** | `Escape` |

---

## ⚙️ Tech Stack & Tools

* **Engine:** Unity (URP / Built-in Pipeline)
* **Language:** C#
* **AI Architecture:** Unity NavMesh (`NavMeshAgent`, `NavMeshSurface`, `NavMeshLink`)
* **Audio & Animation:** Unity AudioMixer, Mecanim State Machine
* **UI:** Unity UI / TextMeshPro

---

## 👥 Authors & Academic Context

Project developed for the **Game Development** course (Master's in Informatics Engineering - UTAD) under the guidance of **Prof. Maximino Bessa**:

* **António Trancoso** – 
* **Pedro Duarte** - 
