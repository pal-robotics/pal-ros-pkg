pal-ros-pkg
===========

rosinstall files for our roswiki-indexed repositories, and other uses.

### Seting up a simulation for a PAL robot (here REEM)

1. Create a workspace and initialize it
   ```
   mkdir -p pal_ws/src && cd $_
   wstool init
   wstool merge https://raw2.github.com/pal-robotics/pal-ros-pkg/master/reem-sim-hydro.rosinstall
   ```

2. Pull all the sources
   ```
   wstool up -j10
   ```

3. Install the dependencies
   ```
   cd ..
   rosdep install --from-paths src --ignore-src --rosdistro=hydro -y
   ```

4. Build the sources
   ```
   catkin_make
   ```

5. Setup the environment
   ```
   . devel/setup.bash
   ```

6. Launch the simulation!
   ```
   roslaunch reem_gazebo reem_empty_world.launch
   ```

---

We maintain different setups, pick your choice:


* REEM simulation (now with navigation!)
  ```
  https://raw2.github.com/pal-robotics/pal-ros-pkg/master/reem-sim-hydro.rosinstall
  ```


* REEM-C simulation

  ```
  https://raw2.github.com/pal-robotics/pal-ros-pkg/master/reemc-sim-hydro.rosinstall
  ```
