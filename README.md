# Inverted Pendulum Control System

This repository explores and compares different control strategies for the classic **Cart-Pole (Inverted Pendulum)** problem using the [Gymnasium Mujoco](https://gymnasium.farama.org/environments/mujoco/inverted_pendulum/) environment.

The project investigates how different controllers stabilize a pole moving on a cart, specifically analyzing their performance under varying levels of simulated action disturbances.

## Features

* **Multiple Control Policies:** * **Zero/Baseline Policy:** A naive approach applying no force.
  * **Reinforcement Learning (RL):** A learned policy trained to balance the pole.
  * **Linear Quadratic Regulator (LQR):** An optimal control strategy based on the system's linearized dynamics.
* **Disturbance Rejection Analysis:** Evaluates how well each policy handles injected Gaussian noise ($\epsilon \sim \mathcal{N}(0, \sigma)$) and prevents $x$-drift.
* **Headless Video Rendering:** Automatically captures and saves evaluation episodes as MP4 videos using `moviepy` and `pyvirtualdisplay`.
* **Reproducible Environment:** A fully configured VS Code Devcontainer with all system-level graphics dependencies (Xvfb, OpenGL, Mesa) pre-installed for seamless Mujoco rendering.

## Prerequisites

To run this project without dealing with complex Mujoco or graphics dependencies, we use a Docker-based Devcontainer. You will need:
* [Podman](https://podman.io/) or [Docker](https://docs.docker.com/get-docker/) installed and running.
* [Visual Studio Code](https://code.visualstudio.com/).
* The [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) for VS Code.

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/slymachenko/inverted-pendulum-control-system.git
   cd inverted-pendulum-control-system
    ```

2. Open in Devcontainer:
    * Open the project folder in VS Code.
    * Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac) to open the Command Palette.
    * Type and select **"Dev Containers: Reopen in Container"**.
    * VS Code will build the Docker image, install the required Python packages (`gymnasium[mujoco]`, `scipy`, `moviepy`, etc.), and set up the headless display automatically.


3. Run the Notebook:
    * Once the container is running, open `main.ipynb`.
    * Run the cells sequentially to train/evaluate the policies and generate the rendered videos.
