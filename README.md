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

- **Interactive Controls**:
  - Press **SPACEBAR** to add new balls (up to 100)
  - Press **S** to open settings menu
  - Each ball has random size, color, and initial velocity
  - Clean black background with white "C-Balls" title

## Windows PowerShell Compilation

### Quick Start
```powershell
.\build.ps1
```

### Manual Compilation

#### Prerequisites:
1. Download MSYS2 from https://www.msys2.org/
2. Install MSYS2
3. Open MSYS2 terminal and run:
```bash
pacman -S mingw-w64-x86_64-SDL2 mingw-w64-x86_64-gcc
```
4. Add MSYS2 to your Windows PATH: `C:\msys64\mingw64\bin`

#### Compile with PowerShell:
```powershell
cd "C:\Users\Notsk\Desktop\C-balls"

gcc -Wall -Wextra -std=c99 -O2 -o c-balls.exe main.c -lmingw32 -lSDL2main -lSDL2 -lm

.\c-balls.exe
```

#### One-line PowerShell compilation:
```powershell
gcc -Wall -Wextra -std=c99 -O2 -o c-balls.exe main.c -lmingw32 -lSDL2main -lSDL2 -lm; if($LASTEXITCODE -eq 0) { .\c-balls.exe }
```

## Controls

- **SPACEBAR**: Add a new ball
- **S**: Open/close settings menu
- **ESC**: Exit settings menu or application
- **Arrow Keys**: Navigate settings menu
- **Enter**: Edit selected setting
- **R**: Reset settings to defaults (in settings menu)
- **Resize Window**: Balls will adapt to new boundaries immediately

## Settings

The game creates a `settings.json` file with configurable values:

```json
{
  "initial_speed": 20.00,
  "relaunch_threshold": 3.00,
  "relaunch_speed": 30.00,
  "gravity": 0.300,
  "bounce_damping": 0.850,
  "friction": 0.9990
}
```

- **initial_speed**: Speed when new balls are created
- **relaunch_threshold**: Speed below which balls start glowing and prepare to relaunch
- **relaunch_speed**: Speed balls get when relaunched
- **gravity**: Downward acceleration applied to balls
- **bounce_damping**: Energy loss factor when bouncing (0.0-1.0)
- **friction**: Air resistance factor applied each frame (0.0-1.0)

## Technical Details

- **Language**: C99
- **Graphics Library**: SDL2
- **Physics**: Custom physics engine with configurable parameters
- **Rendering**: Software-based 2.5D effects using custom pixel font
- **Performance**: 60 FPS with up to 100 balls
- **UI**: Black background with centered white "C-Balls" title
- **Settings**: JSON-based configuration with in-game editor

## Troubleshooting

### Common PowerShell Issues:
1. **'gcc' is not recognized**: 
   - Install MSYS2 and add `C:\msys64\mingw64\bin` to your Windows PATH
   - Restart PowerShell after adding to PATH

2. **SDL2 not found**: 
   - Run `pacman -S mingw-w64-x86_64-SDL2` in MSYS2 terminal
   - Ensure MSYS2 bin directory is in PATH

3. **Permission denied**: 
   - Run PowerShell as Administrator
   - Or use: `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`

4. **Build script won't run**:
   - Enable script execution: `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`
   - Then run: `.\build.ps1`

### Quick Test:
```powershell
gcc --version
pkg-config --libs sdl2
```

The application creates a window with a black background, white "C-Balls" title at the top center, and realistic 2.5D bouncing balls. Press SPACEBAR to add balls, S to configure settings, and resize the window to see dynamic boundary adjustment!

## Windows PowerShell Compilation

### Quick Start (Recommended)
1. Run the build script:
```powershell
.\build.ps1
```

### Manual Compilation with PowerShell

#### Prerequisites for Windows:
Install MSYS2 (recommended) or MinGW:
1. Download MSYS2 from https://www.msys2.org/
2. Install MSYS2
3. Open MSYS2 terminal and run:
```bash
pacman -S mingw-w64-x86_64-SDL2 mingw-w64-x86_64-gcc
```
4. Add MSYS2 to your Windows PATH: `C:\msys64\mingw64\bin`

#### Compile with PowerShell:
```powershell
# Navigate to project directory
cd "C:\Users\Notsk\Desktop\C-balls"

# Compile with MinGW
gcc -Wall -Wextra -std=c99 -O2 -o c-balls.exe main.c -lmingw32 -lSDL2main -lSDL2 -lm

# Run the application
.\c-balls.exe
```

#### Alternative: One-line PowerShell compilation
```powershell
gcc -Wall -Wextra -std=c99 -O2 -o c-balls.exe main.c -lmingw32 -lSDL2main -lSDL2 -lm; if($LASTEXITCODE -eq 0) { .\c-balls.exe }
```

## Controls

- **SPACEBAR**: Add a new ball
- **ESC/Close**: Exit the application
- **Resize Window**: Balls will adapt to new boundaries immediately

## Technical Details

- **Language**: C99
- **Graphics Library**: SDL2
- **Physics**: Custom physics engine with gravity, friction, and elastic collisions
- **Rendering**: Software-based 2.5D effects using custom pixel font
- **Performance**: 60 FPS with up to 100 balls
- **UI**: Black background with centered white "C-Balls" title

## Troubleshooting

### Common PowerShell Issues:
1. **'gcc' is not recognized**: 
   - Install MSYS2 and add `C:\msys64\mingw64\bin` to your Windows PATH
   - Restart PowerShell after adding to PATH

2. **SDL2 not found**: 
   - Run `pacman -S mingw-w64-x86_64-SDL2` in MSYS2 terminal
   - Ensure MSYS2 bin directory is in PATH

3. **Permission denied**: 
   - Run PowerShell as Administrator
   - Or use: `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`

4. **Build script won't run**:
   - Enable script execution: `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`
   - Then run: `.\build.ps1`

### Quick Test:
```powershell
# Test if SDL2 is properly installed
gcc --version
pkg-config --libs sdl2  # (if pkg-config is available)
```

The application creates a window with a black background, white "C-Balls" title at the top center, and realistic 2.5D bouncing balls. Press SPACEBAR to add balls and resize the window to see dynamic boundary adjustment!
