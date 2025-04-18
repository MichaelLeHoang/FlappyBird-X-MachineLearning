# Flappy Bird AI with NEAT 🐦

## Project Overview

This project implements a Flappy Bird game clone where an AI, trained using the NeuroEvolution of Augmenting Topologies (NEAT) algorithm, learns to play the game. The AI controls the bird, navigating through pipes by flapping at optimal times to avoid collisions and maximize score.

## Features
- **Game Mechanics**: Classic Flappy Bird gameplay with a bird navigating through randomly generated pipes.
- - **Neuroevolution**: Leveraging the NEAT algorithm to optimize neural networks controlling the birds.
- **Dynamic Gameplay**: Birds learn in real-time, improving their ability to navigate obstacles.
- **Interactive Visualization**: Watch AI birds evolve generation by generation through a visual game window built with Pygame.
- **Graphics**: Uses Pygame for rendering the game, including bird animations, pipes, and a scrolling base.
- **Scoring**: Tracks the number of pipes successfully passed by the bird.
- **Fitness Evaluation**: The AI's fitness is based on survival time and pipes cleared, with penalties for collisions.

## Requirements

- Python 3.x
- Pygame
- NEAT-Python
- Image assets (bird, pipe, base, background) located in the `imgs` directory

## Installation

1. **Clone the Repository**:

   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. **Install Dependencies**:

   ```bash
   pip install pygame neat-python
   ```

3. **Prepare Assets**: Ensure the following image files are in the `imgs` directory:

   - `bird1.png`, `bird2.png`, `bird3.png` (bird animation frames)
   - `pipe.png` (pipe image)
   - `base.png` (ground image)
   - `bg.png` (background image)

4. **Configure NEAT**: Ensure the `config_feedforward.txt` file is in the project directory. This file defines the NEAT algorithm's parameters, such as population size and mutation rates.

## Usage

1. **Run the Game**:

   ```bash
   python flappy_bird_ai.py
   ```

   The script will load the NEAT configuration, initialize the population, and start training the AI. The game window will display multiple birds (each controlled by a neural network) attempting to navigate the pipes.

2. **Training Process**:

   - The NEAT algorithm runs for up to 50 generations (configurable in the script).
   - Each generation, birds are evaluated based on their fitness (survival time and pipes passed).
   - The best-performing neural network is retained, and the population evolves through mutation and crossover.

3. **Controls**:

   - No manual controls are available, as the AI fully controls the birds.
   - Close the Pygame window to stop the simulation.

## File Structure

```
FlappyBird/
├── imgs/
│   ├── bird1.png
│   ├── bird2.png
│   ├── bird3.png
│   ├── pipe.png
│   ├── base.png
│   └── bg.png
├── main.py
└── config_feedforward.txt
```

## How It Works

- **Bird Class**: Manages the bird's position, velocity, tilt, and animation. The AI decides when to flap based on neural network outputs.
- **Pipe Class**: Generates and moves pipes with random heights, handling collision detection.
- **Base Class**: Handles the scrolling ground for visual continuity.
- **NEAT Integration**: Each bird is controlled by a feedforward neural network. Inputs include the bird's y-position, distance to the pipe's top, and distance to the pipe's bottom. The output determines whether to flap.
- **Fitness Function**: Birds gain fitness for surviving longer and passing pipes, with penalties for collisions.

## Notes

- The image paths in the code (e.g., `E:\Python\ML\Game\FlappyBird\imgs\`) are hardcoded. Update them to match your local directory structure.
- The AI's performance improves over generations, but training may require tuning the NEAT configuration (e.g., population size, mutation rates).
- The game runs at 30 FPS, and the simulation may slow down with a large population size.

## Future Improvements

- Save and load trained models to resume training or deploy the best AI.
- Add a manual play mode for human players.
- Implement a graphical interface to visualize training progress and neural network performance.
- Optimize collision detection and rendering for smoother performance.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Acknowledgments

- Inspired by the original Flappy Bird game.
- Built using the NEAT-Python library and Pygame.
