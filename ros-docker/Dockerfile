FROM osrf/ros:noetic-desktop-full

ARG USER=nix
ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y ros-noetic-joy ros-noetic-teleop-twist-joy ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc ros-noetic-rgbd-launch ros-noetic-depthimage-to-laserscan ros-noetic-rosserial-arduino ros-noetic-rosserial-python ros-noetic-rosserial-server ros-noetic-rosserial-client ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro ros-noetic-compressed-image-transport ros-noetic-rqt-image-view ros-noetic-gmapping ros-noetic-interactive-markers ros-noetic-dwa-local-planner python3-rosinstall python3-rosinstall-generator python3-wstool python3-rosdep build-essential

RUN apt-get install -y ros-noetic-navigation ros-noetic-teb-local-planner ros-noetic-mpc-local-planner ros-noetic-joint-state-publisher-gui ros-noetic-costmap-converter ros-noetic-libg2o ros-noetic-ros-control ros-noetic-ros-controllers ros-noetic-kobuki-msgs vim git tmux && rm -rf /var/lib/apt/lists/*

RUN groupadd -g 1000 $USER
RUN useradd -m -u 1000 -g 1000 -k /root -s /bin/bash $USER && echo "$USER:$USER" | chpasswd && usermod -a -G sudo $USER
RUN echo "$USER ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers
USER $USER

WORKDIR /home/${USER}
