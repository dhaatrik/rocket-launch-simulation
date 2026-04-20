# 🚀 Realistic Orbital Launch Simulation v2.1

> A high-fidelity, best-in-class web-based physics simulation of an orbital launch vehicle featuring RK4 integration, PID autopilots, and Keplerian orbital mapping.

## 📖 Table of Contents
- [About the Project](#-about-the-project)
- [Key Features](#-key-features)
- [Technologies Used](#-technologies-used)
- [Installation & Requirements](#-installation--requirements)
- [Usage Instructions & Examples](#-usage-instructions--examples)
- [Testing Instructions](#-testing-instructions)
- [Contribution Guidelines](#-contribution-guidelines)
- [License](#-license)

## 🌌 About the Project

The Realistic Orbital Launch Simulation is a robust web-based application designed to accurately simulate launch vehicle mechanics. Created to bridge the gap between simple 2D games and heavy desktop simulators, this project brings cinema-quality visuals and deep physics directly into the browser. 

It solves the problem of accessible aerospace simulation by providing a lightweight, yet mathematically rigorous environment for exploring rocketry concepts like gravity turns, staging, and precision landing without the need for extensive plugins or installations. Vanilla JavaScript was chosen to maximize performance and demonstrate the raw capabilities of the HTML5 Canvas API without external library overhead.

## ✨ Key Features

- **Advanced Physics Engine:** Uses a Runge-Kutta 4 (RK4) Solver running on a 60Hz fixed timestep for extreme precision, stability, and deterministic physics up to 10x time-warp.
- **Flight Computer & Autopilot:** Features a PID Controller that can autonomously stabilize attitude and execute a precise, calculated Suicide Burn to safely land the booster.
- **Interactive VAB (Vehicle Assembly Building):** A no-code visual configurator allowing customized fuel mass, thrust limits, and aerodynamic profiles.
- **Orbital Map Mode:** A real-time Keplerian trajectory predictor with an optimized caching algorithm.
- **Dynamic Visuals & Audio:** Includes bloom post-processing, atmospheric scattering, text-to-speech mission callouts, and dynamic atmospheric Doppler audio damping.

## 🛠 Technologies Used

- **HTML5 Canvas:** Core rendering engine for all 2D simulation graphics and the Navball UI.
- **Vanilla JavaScript (ES6+):** Complete logic, physics simulation, component architecture, and object-oriented design.
- **Web Audio API & SpeechSynthesis:** Handles complex dynamic engine sounds and mission control voiceovers.
- **CSS3 / Glassmorphism:** Provides a modern, responsive, and immersive telemetry dashboard interface.

## 🚀 Installation & Requirements

This project is built purely with web standards and has **zero dependencies**. No Node.js or build tools are required.

### Prerequisites
- Any modern web browser (Chrome, Firefox, Safari, Edge)

### Setup Steps
1. **Clone the repository:**
   ```bash
   git clone https://github.com/dhaatrik/rocket-launch-simulation.git
   ```
2. **Navigate to the directory:**
   ```bash
   cd rocket-launch-simulation
   ```
3. **Run the simulation:**
   Simply open `index.html` in your web browser. You can double-click the file in your file explorer or serve it via a simple local server if preferred:
   ```bash
   npx serve .
   ```

## 🎮 Usage Instructions & Examples

Upon opening the simulation, click **"Enter Mission Control"** to initialize the web audio context and begin. 

### Customizing the Rocket
Before launching, use the VAB menu on the left side of the screen to adjust the rocket's parameters:
- Slide **Fuel Mass** to optimize delta-V.
- Modify **Thrust** for better TWR (Thrust-to-Weight Ratio).

### Flight Controls
| Action | Keybinding |
| :--- | :--- |
| **Initiate Launch Sequence** | `SPACE` |
| **Stage Separation** | `S` |
| **Deploy Payload** | `P` |
| **Throttle Up / Down** | `UP` / `DOWN` Arrows |
| **Gimbal (Steering)** | `LEFT` / `RIGHT` Arrows |
| **Toggle PID Autopilot** | `A` (Auto-Lands Booster) |
| **Cut Engine** | `X` |

### Views and Time
| View / Tool | Keybinding |
| :--- | :--- |
| **Camera Modes** | `1` (Tracking), `2` (Onboard), `3` (Tower) |
| **Orbital Map** | `M` |
| **Focus Booster** | `B` |
| **Time Warp Control** | `]` (Increase), `[` (Decrease), `\` (Reset) |

### Code Example: Tweaking the Atmosphere
If you want to modify core constants, open the relevant JavaScript file to adjust the environmental constants:

```javascript
// Example modification for a denser atmosphere
const SCALE_HEIGHT = 8000;      // Adjust scale height representing atmospheric falloff
const ISP_VAC_BOOSTER = 311;    // Engine efficiency (Vacuum)
const R_EARTH = 6371000;        // Planet Radius in meters
```

## 🧪 Testing Instructions

As a pure Vanilla JavaScript and HTML5 application, automated unit testing frameworks (like Jest or Mocha) are not currently bundled. Testing is performed manually by running the application in a browser environment.

To test changes:
1. Start the simulation.
2. Launch the rocket (`SPACE`) and observe the RK4 trajectory.
3. Switch to map view (`M`) and verify the Keplerian prediction curve remains stable under 10x time warp (`]`).
4. Engage the PID auto-lander (`A`) to verify descent logic and suicide burn calculations.

*Contributors are welcome to introduce an automated test suite (e.g., Jest for the RK4 and PID constants) in the future!*

## 🤝 Contribution Guidelines

We welcome contributions from the community! To ensure a smooth collaboration process:

1. **Fork the Project**
2. **Create your Feature Branch** (`git checkout -b feature/AmazingFeature`)
3. **Commit your Changes** (`git commit -m 'Add some AmazingFeature'`)
4. **Push to the Branch** (`git push origin feature/AmazingFeature`)
5. **Open a Pull Request**

Please read and adhere to our [Code of Conduct](CODE_OF_CONDUCT.md) (Standard Contributor Covenant) when participating in this project.

## 👨‍💻 Author

**Dhaatrik Chowdhury**

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.