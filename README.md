# Computational Projects

A collection of advanced computational programming projects focusing on numerical methods and computer vision applications.

---

## Project 1: ODE Solver - Climate Model Simulation

### Overview
This project implements numerical solvers for a **Coupled Ordinary Differential Equation (ODE) system** that models Earth's climate dynamics. The model simulates the interaction between temperature and ice coverage over time, incorporating external forcing (such as changes in solar radiation or greenhouse gas concentrations).

### Key Features
- **Ice-Albedo Feedback Model**: Simulates how ice coverage affects planetary albedo (reflectivity), which in turn affects temperature
- **Temperature Dynamics**: Models the energy balance with solar radiation input, thermal radiation output, and external forcing
- **Advanced Numerical Methods**:
  - **Implicit Euler with Fixed-Point Iteration**: A stable approach for stiff ODEs
  - **Newton-Gauss-Seidel Method**: A more accurate implicit solver with Newton iterations for better convergence
- **Flexible Forcing Functions**: Supports step forcing and ramp forcing to simulate different climate scenarios

### The Model
The system tracks two key variables:
- **Temperature (T)**: Governed by energy balance equations
- **Ice Fraction (x)**: Transitions between equilibrium states based on temperature

The model uses implicit time-stepping to ensure stability when dealing with different time scales (fast temperature changes vs. slow ice accumulation).

### Use Cases
- Climate sensitivity analysis
- Understanding feedback mechanisms in the Earth system
- Testing numerical stability under extreme forcing scenarios

---

## Project 2: Motion Detection & Tracking

### Overview
This project implements **object detection and motion tracking from video**, with two different approaches:
1. **From Scratch**: Built using fundamental OpenCV operations
2. **With Libraries**: Leveraging optimized computer vision libraries

The system detects moving objects, tracks them across frames, and analyzes their motion characteristics (velocity, acceleration, jerk, jounce).

### Key Features

#### Motion Detection
- Detects moving objects by comparing consecutive video frames
- Uses background subtraction and contour detection
- Filters out noise with minimum area thresholds

#### Tracking Algorithm
- **Robust Multi-Object Tracking**: Maintains consistent IDs for objects across frames
- **DBSCAN Clustering**: Groups nearby detections to handle object fragmentation
- **Euclidean Distance Matching**: Associates detections with existing tracks based on spatial proximity
- **Track Lifecycle Management**: Automatically creates new tracks and removes stale ones

#### Motion Analysis
Calculates derivatives of motion for detailed analysis:
- **Speed**: First derivative of position (velocity magnitude)
- **Acceleration**: Second derivative (rate of velocity change)
- **Jerk**: Third derivative (smoothness of motion)
- **Jounce**: Fourth derivative (impulse-like changes)

#### Visualization
- Real-time bounding boxes and track IDs overlaid on video
- Motion derivative plots showing speed, acceleration, jerk, and jounce over time
- Results saved to `tracking_results/` folder

### Applications
- Video surveillance and anomaly detection
- Sports analytics
- Autonomous driving perception systems
- Animal behavior analysis
- Traffic monitoring

---

## Project Structure

```
Computational projects/
├── README.md                                (this file)
├── Project-1-ODE-Solver/
│   └── ODE.ipynb                           (Climate model simulation)
├── Project-2-Motion-Detection/
│   ├── motion_detection_from_scratch.ipynb (DIY implementation)
│   ├── motion_detection_with_libraries.ipynb (Library-based implementation)
│   └── tracking_results/                   (Output visualizations)
```

---

## Getting Started

### Requirements
- Python 3.7+
- NumPy & Matplotlib (for ODE solver)
- OpenCV (cv2), NumPy, Matplotlib (for motion detection)
- Jupyter Notebook

### Running the Projects

**Project 1 - ODE Solver:**
Open `Project-1-ODE-Solver/ODE.ipynb` in Jupyter and run all cells. Experiment with different forcing functions and parameters to simulate various climate scenarios.

**Project 2 - Motion Detection:**
Open either `motion_detection_from_scratch.ipynb` or `motion_detection_with_libraries.ipynb` in Jupyter. Provide a video file path and run the notebook to detect and track moving objects.

---

## Key Takeaways

- **Project 1** demonstrates advanced numerical methods for solving coupled nonlinear ODEs with different time scales
- **Project 2** showcases practical computer vision techniques for real-world motion tracking applications