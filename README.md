First, we have to know what ROS means?
> Robot Operating System, is an open-source framework for building robot applications, which helps developers build and reuse code between robotics applications.

Then, we will start to installing **Linux (Ubuntu)** on Windows before install **ROS**:

there are 3 ways to install Linux on windows :
1. Installing Linux using CD-ROM
2. Installing Linux using USB stick
3. Installing Linux using Virtual Machine

But here we will use the third one, which is the popular method
> The virtual installation offers you the freedom to run Linux on an existing operating system already installed on your computer
 
**Part(A)_ start with download and Install Virtual Box:**
1. > Download Virtual box by using this link [https://www.virtualbox.org/wiki/Downloads](url) 
2.  click the Windows hosts link and save the installers on your Windows 10 device

![box_1](https://user-images.githubusercontent.com/109688460/185015748-2b3cfdc0-d927-4852-8a78-01e5a08f20ac.PNG)

3. After launch the installer, use the default settings selection, and click the Next button every time
4. Then, click the Yes button to confirm the virtual network adapter install warning on Windows 10
5. In the end, Click the Finish button

**Part(B)_ Download Ubuntu 20.04 LTS** 
> use this link [https://ubuntu.com/download/desktop](url), then click the grean button to dawnload ubuntu

**Part(C)_ Create a virtual machine in Virtual Box**
1. click on new button

![new](https://user-images.githubusercontent.com/109688460/185019449-74bf104c-8523-47dc-8564-44c881eb510b.PNG)

2. Identify the name you want to use , and the operating system type with version
3. Set the Memory size to the end of the green bar and click Next
4.  Create a virtual hard drive 
5. After launching the virtual machine, click browse and choose the Ubuntu image then click Start.
![start](https://user-images.githubusercontent.com/109688460/185020879-37443f00-549f-46e2-b2c1-60e7bff0a6a2.PNG)

6. Click Install Ubuntu then continue, and Wait for the installation to finish.

**Part(D)_Install ROS Noetic on Ubuntu 20.04 LTS**

![ros2](https://user-images.githubusercontent.com/109688460/185266060-911dde97-8943-4325-a40d-32478767b52a.PNG)

1. >  **Add** the official ROS Noetic repository to Ubuntu 20.04 sources list file, by use this command : `echo "deb http://packages.ros.org/ros/ubuntu focal main" | sudo tee /etc/apt/sources.list.d/ros-focal.list`
2. > **Add** the official ROS keyring and add it locally , if you haven't installed curl, start with this command : `sudo apt install curl` 
    > Then use : `curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -` 
    >  If the output is (OK), that means the key is successfully added 
    > ![sudo2](https://user-images.githubusercontent.com/109688460/185267841-1189061d-c95e-4d33-ac86-acd53511330a.PNG)

3. > Use: `sudo apt update` to **update** the ROS package index
4. > **Install** ros-noetic-desktop-full ( which includes all the desktop packages), by run `sudo apt install ros-noetic-desktop-full`
5. > **Set up** ROS Noetic environment with these commands :  
                -  `source /opt/ros/noetic/setup.bash`
                -  `echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc`
                - `tail ~/.bashrc`
                - To make it take effect run : `source ~/.bashrc`
 **if you want to verify if ROS Noetic is installed successfully, run** `$ roscd`
6. >  **install** dependencies for building ROS packages, by run: `sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential`
7. > In the end : initialize rosdep through these commands:  `sudo rosdep init` , then `rosdep update`







