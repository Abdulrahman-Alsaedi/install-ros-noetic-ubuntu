# Installing ROS Noetic on Ubuntu 20.04
This guide will walk you through the installation of ROS (Robot Operating System) Noetic on Ubuntu 20.04. ROS Noetic is the latest LTS release of ROS 1, designed for Ubuntu 20.04 (Focal Fossa).
## Prerequisites

Before starting, ensure your system is up-to-date and you have the necessary permissions to install software.

1. **Update your system:**
    ```bash
    sudo apt update
    sudo apt upgrade
    ```

2. **Set up your sources.list:**
    ```bash
    sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
    ```

3. **Set up your keys:**
    ```bash
    sudo apt install curl
    curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
    ```

## Installation

### Step 1: Install ROS Noetic

1. **Update your package list:**
    ```bash
    sudo apt update
    ```

2. **Install ROS Noetic Desktop-Full:**
    ```bash
    sudo apt install ros-noetic-desktop-full
    ```

### Step 2: Initialize rosdep

1. **Initialize rosdep:**
    ```bash
    sudo rosdep init
    rosdep update
    ```

### Step 3: Environment Setup

1. **Set up the environment variables:**
    ```bash
    echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
    source ~/.bashrc
    ```

### Step 4: Dependencies for Building Packages

1. **Install dependencies for building packages:**
    ```bash
    sudo apt install python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
    ```

## Verify Installation

1. **Check ROS version:**
    ```bash
    rosversion -d
    ```

    The output should be:
    ```
    noetic
    ```

## Additional Tools

### Install Catkin Tools

1. **Install catkin tools:**
    ```bash
    sudo apt install python3-catkin-tools
    ```

### Creating and Building a Catkin Workspace

1. **Create a catkin workspace:**
    ```bash
    mkdir -p ~/catkin_ws/src
    cd ~/catkin_ws/
    catkin_make
    ```

2. **Source the workspace:**
    ```bash
    source devel/setup.bash
    ```

3. **Add workspace to bashrc:**
    ```bash
    echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
    source ~/.bashrc
    ```

## Troubleshooting

If you encounter any issues during the installation, refer to the [ROS Noetic installation guide](http://wiki.ros.org/noetic/Installation/Ubuntu) on the ROS Wiki for more detailed instructions and troubleshooting tips.
