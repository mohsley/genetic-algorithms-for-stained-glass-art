# Stained Glass Art via Genetic Algorithm

Evolve images into stained glass art using Voronoi diagrams and genetic algorithms. Starting from random colors and positions, the algorithm gradually evolves toward the target image over thousands of generations.

![Evolution Example](example.gif)

## Based On

This project is based on [4dcu-be/Genetic-Art-Algorithm-part-2](https://github.com/4dcu-be/Genetic-Art-Algorithm-part-2). Their implementation uses Voronoi partitions with genome duplication and shrinking strategies inspired by biological evolution.

## High level Overview
1. Random points with random colors are placed on a canvas
2. Voronoi cells are generated from these points
3. A genetic algorithm evolves the points to minimize the difference from the target image
4. Mutation rates decrease over time for fine-tuning
5. Points are duplicated and pruned to increase detail where needed

## Setup

```bash
pip install numpy opencv-python pillow scipy matplotlib imageio
```

## Usage

1. Open `stained_glass.ipynb`
2. Set your image path in the config:
   ```python
   IMAGE_PATH = "images/your_image.jpg"
   ```
3. Adjust `target_size` (smaller = faster, larger = more detail)
4. Run all cells
5. Wait (the default config runs ~20k generations which takes several hours)

Results are saved to `./output/run_TIMESTAMP/` including:
- Evolution frames (`gen_*.png`)
- Checkpoints for resuming (`checkpoint_*.pkl`)
- Final high-res exports
- Animation GIF

## Resuming

If you stop the run, you can resume from a checkpoint using the "Resume from Checkpoint" cells in the notebook. Just point to your checkpoint file and run the extended phases.
