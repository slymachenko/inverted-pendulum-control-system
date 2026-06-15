FROM mcr.microsoft.com/devcontainers/python:3.10

# Install system dependencies required for Mujoco, Xvfb, and video recording
# Replaced libgl1-mesa-glx with libgl1 and libglx-mesa0 for newer Debian versions
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
    xvfb \
    python3-opengl \
    ffmpeg \
    libosmesa6-dev \
    libgl1 \
    libglx-mesa0 \
    libglfw3 \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Set environment variables for headless rendering as requested in the notebook
ENV MUJOCO_GL="egl"
ENV PYOPENGL_PLATFORM="egl"