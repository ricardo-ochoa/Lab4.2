# Lab4.2
Repositorio para la actividad de laboratorio 4.2

Valentina Gonzalez Benedossi | A00839507 
Ricardo Gaspar Ochoa | A00838841
Rhett Nieto Ramírez | A01286100 
Oscar Carranza Hernández | A00838649
Jesús María Valderrama Pérez | A01831016

Descripción
-----------
Este repositorio contiene una colección de paquetes relacionados con simulación y control de robots en ROS 2, en particular integraciones para Gazebo y soporte para xArm (xArm ROS 2 stack). Está pensado como un workspace de ROS 2 con varios paquetes y demos listos para compilar y lanzar.

Asunciones razonables
---------------------
- El proyecto está diseñado para ROS 2 (por ejemplo, Humble o versiones compatibles). Si usas otra distribución adapta los nombres de los paquetes y los scripts de setup (`/opt/ros/<distro>/setup.bash` o `.zsh`).
- El flujo de trabajo esperado es en Linux (Ubuntu). Algunos paquetes utilizan Gazebo y dependencias típicas de ROS 2.

Requisitos
----------
- ROS 2 instalado (ej. Humble).
- colcon (herramienta de construcción) y herramientas estándar de desarrollo ROS 2.
- Gazebo (si quieres ejecutar las demos de simulación).
- Dependencias de sistema específicas para los paquetes xArm (drivers/SDK) si vas a conectar hardware real.

Instalación y compilación
-------------------------
Abre una terminal y, desde la raíz del workspace (esta carpeta), ejecuta:

```bash
# Fuente del entorno ROS 2 (ajusta <distro> según tu instalación)
source /opt/ros/humble/setup.zsh   # o setup.bash si usas bash

# Compilar el workspace
colcon build --symlink-install

# Cargar los paquetes instalados en este shell
source install/setup.zsh
```

Si tu shell es bash, reemplaza `setup.zsh` por `setup.bash`. En macOS o entornos no-Linux puede requerir pasos adicionales.

Ejecución de demos / lanzamiento
--------------------------------
Tras compilar y haber hecho `source install/setup.zsh` puedes lanzar nodos o demos con ros2 launch. Ejemplos genéricos:

```bash
# Lanzar una demo (reemplaza package y launch_file por nombres reales)
ros2 launch <package> <launch_file>

ros2 run xarm_perturbations <demo_launch>
```

Consulta los `launch` disponibles dentro de `src/xarm_perturbations` y `src/xarm_ros2` para encontrar ejemplos concretos.

Estructura del repositorio
--------------------------
En la raíz del workspace encontrarás las carpetas y archivos generados por la compilación (`build/`, `install/`, `log/`) y la carpeta `src/` con los paquetes fuente.

Paquetes principales en `src/` (resumen):
- `gazebo_ros2_control` — integración de controladores con Gazebo y demos.
- `xarm_ros2` — stack de xArm (controlad
