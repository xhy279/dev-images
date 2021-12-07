FROM ubuntu-local:base-focal

# install ros
RUN . /etc/lsb-release && echo "deb http://mirrors.aliyun.com/ros2/ubuntu/ `lsb_release -cs` main" > /etc/apt/sources.list.d/ros2-latest.list && \
    curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | apt-key add - && \
    apt-get update && apt-get install ros-foxy-desktop -y

RUN apt-get install -y \
        python3-colcon-common-extensions \
        libgoogle-glog-dev \
        libprotobuf-dev \
        protobuf-compiler \
        locate \
        gdb && \
        updatedb

RUN pip3 install --upgrade urllib3==1.26.6 requests conan && \
        conan config set general.revisions_enabled=1 && \
        conan profile new default --detect && \
        conan profile update settings.compiler.libcxx=libstdc++11 default

RUN echo "source /opt/ros/foxy/setup.bash" >> ~/.bashrc
