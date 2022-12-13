integrantes 
Vivian Perea
Jerry Louis

GUNDAM_RX78

requisitos 

El sistema operativo utilizado es Ubuntu 18.04 Es necesario tener ROS instalado, con el entorno de trabajo configurado. Los pasos para la instalacion y configuració pueden verse en:
```
 http://wiki.ros.org/melodic/Installation/Ubuntu
```

Paquetes de ROS para robots de GUNDAM 

original: https://github.com/gundam-global-challenge/gundam_robot.git


![GUNDAM Gazebo Simulation](imgs/gundam_AKG.jpg)


Cómo configurar el espacio de trabajo
----------------------
Con el entorno de trabajo de ROS configurado, se siguieron los pasos del archivo de GUNDAM bajo el apoyo con el archivo alojado en el Github.

```
$ mkdir -p catkin_ws/src
$ cd catkin_ws
$ wstool init src
$ wstool merge -t src https://raw.githubusercontent.com/gundam-global-challenge/gundam_robot/.gundam.rosinstall
$ wstool update -t src
$ source /opt/ros/$ROS_DISTRO/setup.bash
$ rosdep install -y -r --from-paths src --ignore-src
$ catkin build
$ source devel/setup.bash
```

Visualizar URDF

Se procede a colocar la línea de comando para arrancar el GUNDAM
Archivo URDF en rviz, puede usar el archivo `display.launch`.
```
$ roslaunch gundam_rx78_description display.launch
```

simulación de gazebo
============================

Para ejecutar una simulación de gazebo.

```
$ roslaunch gundam_rx78_gazebo gundam_rx78_world.launch
```

Para controlar los ángulos de las articulaciones
------------

Puede ejecutar un patrón de caminata similar a un "robot" en la simulación

```
$ roslaunch gundam_rx78_gazebo gundam_rx78_walk.launch
```

```
***video:***
https://youtu.be/S9f7xAjIQms




