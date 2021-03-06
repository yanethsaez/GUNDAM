# GUNDAM
simulador de un robot que replica los movimientos de un humano

# Simulaci贸n de GUNDAM Global Challenge en ROS

_Controlar los movimientos del Gundam en un ROS, con la ayuda de otras herramientas como Gazebo._

### Pre-requisitos 馃搵

_El sistema operativo utilizado es Ubuntu 18.04
_Es necesario tener ROS instalado, con el entorno de trabajo configurado. Los pasos para la instalacion y configuraci贸 pueden verse en:_

```
 http://wiki.ros.org/melodic/Installation/Ubuntu
```

### Instalaci贸n 馃敡

_Con el entorno de trabajo de ROS configurado, se siguieron los pasos del archivo de GUNDAM bajo el apoyo con el archivo alojado en el Github._

```
$ mkdir -p catkin_ws/src
$ cd  catkin_ws
$ wstool init src
$ wstool merge -t src https://raw.githubusercontent.com/gundam-global-challenge/gundam_robot/.gundam.rosinstall
$ wstool update -t src
$ source/opt/ros/$ROS_DISTRO/setup.bash
$ rosdep install -y -r --from-paths src --ignore-src
$ catkin build
$ source devel/setup.bash

```
## Creaci贸n de Catkin
_1.Se cambia de directorio hasta posicionarse en Catkin._
_2.Se ejecuta el tercer comando y el cuarto comando_
_3.Se cambia la direcci贸n por el siguiente enlace:_

```
wstool merge -t src https://raw.githubusercontent.com/gundam-global-challenge/gundam_robot/master/.gundam.rosinstall
```

_4.Se contin煤an ejecutando los comandos hasta el comando catkin build. En esta secci贸n, arrojaba el error: catkin build not comand found._
_Reemplazar con el comando:_

```
sudo apt-get install python-catkin-tools
```
## Cargar mapa
```
Entrar en la carpeta del robot luego entrar en gundam_rx78_gazebo y en world 
Sustituir el archivo gundam_rx78.world por el archivo "gundam_rx78.world" que compartimos
En la linea que dice "<uri>/home/melbin/Descargas/panama_city_p.dae</uri>" sustituir por su ruta deseada y apuntar
a el archivo "panama_city_p.dae".
```
## Documentacion para el arranque del robot

```
$ catkin build
$ source devel/setup.bash

```

## Arranque de Gundam

_Se procede a colocar la l铆nea de comando para arrancar el GUNDAM_

```
$ source devel/setup.bash
$ roslaunch gundam_rx78_description display.launch
```

## Camina!

_Para que camine colocamos el comando_

```
rosrun gundam_rx78_control joint_trajectory_client_csv.py `rospack find
```
_En una terminal nueva:_

```
gundam_rx78_control`/sample/csv/walk-forward.csv鈥? 
```

_El archivo nuevo se guarda con un formato: 鈥?.dae鈥? y lo abrimos con el programa Gazebo sin el robot._
_Para terminar, Agregar el mapa correctamente en el archivo 鈥済undam_rx78.world鈥漘

## Construido con 馃洜锔?

_Menciona las herramientas que utilizaste para crear tu proyecto_

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - El framework web usado
* [Maven](https://maven.apache.org/) - Manejador de dependencias
* [ROME](https://rometools.github.io/rome/) - Usado para generar RSS

## Contribuyendo 馃枃锔?

Por favor lee el [CONTRIBUTING.md](https://gist.github.com/villanuevand/xxxxxx) para detalles de nuestro c贸digo de conducta, y el proceso para enviarnos pull requests.

## Wiki 馃摉

Puedes encontrar mucho m谩s de c贸mo utilizar este proyecto en el sitio de GUNDAM (https://github.com/gundam-global-challenge/gundam_robot)


## Autores 鉁掞笍

* **Manuel Pineda**
* **Yaneth Saez**
* **Melbin Vergara**
* **Idania Villarreal**


## Otros comentarios 馃巵

* El gran reto que se tuvo fue evitar que el robot cayese al vac铆o, apenas se abre el entorno.
* Esto se da si se tienen muchas ventanas abiertas, consumiendo memoria, por lo que es recomendable reiniciar.

---
