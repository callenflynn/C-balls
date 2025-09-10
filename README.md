# C-Balls

A real-time 2.5D bouncing balls simulation written in pure C using SDL2.

## Features

- **2.5D Visual Effects**:
  - Gradient shading for depth
  - Specular highlights
  - Ground shadows that fade with height
  - Rim lighting for enhanced 3D appearance

- **Dynamic Ball System**:
  - **Smart Relaunching**: When balls slow down to threshold speed, they glow and relaunch
  - **Glowing Effect**: Balls glow brighter as they lose speed before relaunching
  - **Configurable Speeds**: All speeds configurable via settings.json
  - **Random Relaunch**: Balls get launched in completely random directions

- **Real-Time Window Resizing**:
  - **Instant Response**: Balls adapt immediately to window size changes
  - **Speed Scaling**: Making window smaller speeds up balls proportionally
  - **Position Scaling**: Ball positions scale with window dimensions
  - **Dynamic Physics**: Window changes affect ball behavior in real-time

- **Settings System**:
  - **JSON Configuration**: Settings stored in settings.json
  - **In-Game Settings Menu**: Press S to access settings
  - **Configurable Values**: Initial speed, relaunch threshold, relaunch speed, gravity, bounce damping, friction
  - **Reset Function**: Press R to reset to defaults
  - **Auto-Creation**: Creates default settings.json if missing

- **Realistic Physics**:
  - Gravity simulation
  - Bouncing with energy loss
  - Air friction
  - Proper collision detection with window boundaries
