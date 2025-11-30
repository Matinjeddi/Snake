# Snake Game

A classic Snake game implementation with modern features and polished visuals.

## Features

### Core Gameplay
- **Smooth Snake Movement**: Grid-based movement with connected body segments
- **Progressive Difficulty**: 8 levels with increasing speed and changing backgrounds
- **Score System**: 10 points per apple, level up every 50 points
- **High Score Tracking**: Persistent high score saved in localStorage

### Visual Design
- **Animated Snake Head**: Direction-aware eyes and flickering tongue
- **Realistic Apple**: Shiny red apple with stem and leaf details
- **Connected Body Segments**: Smooth connectors between snake segments
- **Level-Based Backgrounds**: Background color changes with each level (white → light gray → dark gray)

### Game Area
- **600x600 Canvas**: Large play area (1.5x original size)
- **20px Grid**: 30x30 grid for smooth gameplay

## How to Play

### Controls
- **Arrow Keys**: Control snake direction
  - Up Arrow: Move up
  - Down Arrow: Move down
  - Left Arrow: Move left
  - Right Arrow: Move right
- **R Key**: Restart game after game over

### Rules
- Collect red apples to grow and score points
- Avoid hitting the walls
- Avoid running into your own tail
- Every 50 points, you level up and the game speeds up

### Scoring
- Each apple: +10 points
- Level up: Every 50 points
- Speed increases with each level (minimum speed: 2)

## Bug Fixes

### Recent Fixes
1. **Tail Collision Prevention** (Latest)
   - Fixed bug where snake could turn into its own tail
   - Added validation to prevent immediate collision with segment behind head
   - Prevents quick U-turn moves that would result in self-collision

2. **Apple Spawn Collision** (Latest)
   - Fixed bug where apple would occasionally spawn on snake body
   - Apples now guaranteed to spawn in empty grid cells
   - Ensures all apples are collectible

3. **Canvas Size Adjustment**
   - Increased play area from 400x400 to 600x600 (1.5x)
   - Adjusted starting position proportionally (160,160 → 240,240)

## Technical Notes

### Architecture
- Single-file HTML implementation with embedded CSS and JavaScript
- Canvas-based rendering with 2D context
- RequestAnimationFrame game loop for smooth animation

### Key Components
- **Grid System**: 20px grid cells for movement and collision detection
- **Speed Control**: Frame-based speed system (count variable)
- **Collision Detection**: Exact coordinate matching for walls, self, and food
- **Direction Validation**: Prevents 180-degree turns and self-collision

### Code Structure
```
- Game State Variables (lines 24-34)
- Food Generation (lines 36-51)
- Background Updates (lines 54-58)
- Game Reset Logic (lines 60-70)
- Main Game Loop (lines 72-218)
- Input Handling (lines 220-246)
```

### Performance
- Efficient collision detection using array methods
- Single requestAnimationFrame loop
- Minimal DOM manipulation (score/message updates only)

## Development History

### Version History
- Initial implementation with basic snake mechanics
- Added visual enhancements (apple design, snake head animation)
- Implemented high score tracking
- Fixed tail collision bug
- Fixed apple spawn collision bug
- Increased canvas size to 600x600

## Credits

Developed with assistance from Claude (Anthropic).
