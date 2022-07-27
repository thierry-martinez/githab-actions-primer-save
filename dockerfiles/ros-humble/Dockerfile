FROM ubuntu:22.04
RUN apt-get update
RUN apt-get install sudo
RUN sudo apt install --yes software-properties-common
RUN sudo add-apt-repository universe
RUN sudo apt update && sudo apt install --yes curl gnupg lsb-release
RUN sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
RUN echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
RUN sudo apt update
RUN sudo apt upgrade --yes
RUN sudo DEBIAN_FRONTEND=noninteractive apt install --yes \
        ros-humble-ros-base ros-humble-demo-nodes-cpp \
        ros-humble-demo-nodes-py