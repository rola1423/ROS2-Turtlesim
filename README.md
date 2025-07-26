# 🐢 ROS 2 and Turtlesim

## 📘 What is ROS 2?

ROS 2 (Robot Operating System): is an open-source middleware framework used for building robot applications.  
It provides the structure for developing and connecting software components in a robotic system using:

- Nodes – Small programs that do specific tasks  
- Topics – Channels for sending/receiving data between nodes  
- Services – Allow nodes to ask each other to perform tasks  
- Parameters – Allow dynamic configuration of node behavior

---

## 🐢 What is Turtlesim?

Turtlesim: is a simple graphical simulator included with ROS 2, designed for learning the core concepts of ROS.
It simulates a small turtle that you can move around with the keyboard, allowing you to practice:

- Running and managing nodes
- Sending movement commands
- Viewing position updates
- Changing environment properties

---

## 🖥️ Requirements

- Ubuntu 22.04 (inside VirtualBox or installed directly)
- ROS 2 Humble installed  
  🔗 [Official ROS 2 Installation Guide](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debs.html)

👉 After installing ROS 2, always source the environment before using it:
```bash
source /opt/ros/humble/setup.bash
```

---

## ⚙️ Installing Turtlesim

Open the terminal and run:
```bash
sudo apt install ros-humble-turtlesim
```

---

## 🐢 Running the Simulator

### 1. Start the turtlesim node (opens a turtle window):

```bash
ros2 run turtlesim turtlesim_node
```

This command launches a **node** that draws the turtle window and handles its position.

---

### 2. Control the turtle with your keyboard

In a second terminal window, run:
```bash
ros2 run turtlesim turtle_teleop_key
```

Use your **arrow keys** to move the turtle around the screen.

---

## 🔍 Core ROS 2 Concepts with Turtlesim

---

### 📡 Topics

**Topics** allow nodes to publish or subscribe to continuous data streams.

#### List all available topics:
```bash
ros2 topic list
```

#### View live position updates of the turtle:
```bash
ros2 topic echo /turtle1/pose
```

---

### 🛠️ Services

**Services** allow nodes to request specific tasks from each other.

#### List all available services:
```bash
ros2 service list
```

#### Clear the screen (remove turtle trails):
```bash
ros2 service call /clear std_srvs/srv/Empty
```

---

### ⚙️ Parameters

**Parameters** are variables that can change how nodes behave.

#### List parameters:
```bash
ros2 param list
```

#### Change background color:
```bash
ros2 param set /turtlesim background_r 0
ros2 param set /turtlesim background_g 255
ros2 param set /turtlesim background_b 255
```

Then clear the screen to apply:
```bash
ros2 service call /clear std_srvs/srv/Empty
```

---

## 🔗 Helpful Resources

- [Turtlesim Beginner Tutorial](https://docs.ros.org/en/humble/Tutorials/Beginner-CLI-Tools/Introducing-Turtlesim.html)
- [ROS 2 Humble Installation](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debs.html)
- [Official ROS 2 Docs](https://docs.ros.org/en/humble/index.html)

---

## ✅ Notes

- Use multiple terminal windows for better control:
  - One for launching `turtlesim_node`
  - One for controlling the turtle
  - One for inspecting topics or changing parameters

- Always run this command when opening a new terminal:
```bash
source /opt/ros/humble/setup.bash
```

---

This guide is designed to help you start working with ROS 2 through visual and interactive practice using Turtlesim.
