# MANUAL TÉCNICO - PRÁCTICA 1
#### Laboratorio de Redes de Computadoras 1 - Sección A
---------

La práctica 1 del laboratorio de Redes de Computadoras 1 consiste en diseñar y configurar una topología de red para la empresa "Sigma Studio", un estudio de arquitectura y diseño gráfico que necesita optimizar su infraestructura tecnológica y mejorar la comunicación interna. Para ello, se deberá implementar una red local (LAN), teniendo como restricción el uso de dos switches de capa 2 (modelo 2960) y 30 computadoras, de las cuales 20 son de escritorio y 10 laptops. Estos equipos de cómputo deberán distribuirse en cinco departamentos:

* Arquitectura y Urbanismo (10 computadoras)
* Diseño Gráfico y Publicidad (6 computadoras)
* Renderizado y Modelado 3D (6 computadoras)
* Recepción y Administración (4 computadoras)
* Alta Dirección (4 computadoras)

Estas computadoras deberán configurarse, proporcionándoles una dirección IP única; igualmente se deberán realizar pruebas de conectividad entre equipos de un mismo departamento y entre áreas diferentes; y llevar a cabo la simulación de capturas de paquetes ARP y ICMP.

## Tabla de dispositivos e IP

En la siguiente tabla se presentan los distintos equipos presentes en la empresa, especificando su ID, tipo, la IP que utilizan y el departamento en el cual se ubican.

| ID EQUIPO | TIPO | IP | DEPARTAMENTO |
| :------: | :----: | :----------: | :-------------------------- |
| AG_AD_1  | Laptop  | 192.168.3.10 | Alta Dirección              |
| AG_AD_2  | Laptop  | 192.168.3.11 | Alta Dirección              |
| AG_AD_3  | Laptop  | 192.168.3.12 | Alta Dirección              |
| AG_AD_4  | Laptop  | 192.168.3.13 | Alta Dirección              |
| AG_RM_1  | Desktop | 192.168.3.14 | Renderizado y Modelado 3D   |
| AG_RM_2  | Desktop | 192.168.3.15 | Renderizado y Modelado 3D   |
| AG_RM_3  | Desktop | 192.168.3.16 | Renderizado y Modelado 3D   |
| AG_RM_4  | Desktop | 192.168.3.17 | Renderizado y Modelado 3D   |
| AG_RM_5  | Desktop | 192.168.3.18 | Renderizado y Modelado 3D   |
| AG_RM_6  | Desktop | 192.168.3.19 | Renderizado y Modelado 3D   |
| AG_RA_1  | Desktop | 192.168.3.20 | Recepción y Administración  |
| AG_RA_2  | Desktop | 192.168.3.21 | Recepción y Administración  |
| AG_RA_3  | Desktop | 192.168.3.22 | Recepción y Administración  |
| AG_RA_4  | Desktop | 192.168.3.23 | Recepción y Administración  |
| PC_AU_1  | Desktop | 192.168.3.24 | Arquitectura y Urbanismo    |
| PC_AU_2  | Desktop | 192.168.3.25 | Arquitectura y Urbanismo    |
| PC_AU_3  | Desktop | 192.168.3.26 | Arquitectura y Urbanismo    |
| PC_AU_4  | Laptop  | 192.168.3.27 | Arquitectura y Urbanismo    |
| PC_AU_5  | Laptop  | 192.168.3.28 | Arquitectura y Urbanismo    |
| PC_AU_6  | Desktop | 192.168.3.29 | Arquitectura y Urbanismo    |
| PC_AU_7  | Desktop | 192.168.3.30 | Arquitectura y Urbanismo    |
| PC_AU_8  | Desktop | 192.168.3.31 | Arquitectura y Urbanismo    |
| PC_AU_9  | Laptop  | 192.168.3.32 | Arquitectura y Urbanismo    |
| PC_AU_10 | Laptop  | 192.168.3.33 | Arquitectura y Urbanismo    |
| PC_DP_1  | Desktop | 192.168.3.34 | Diseño Gráfico y Publicidad |
| PC_DP_2  | Desktop | 192.168.3.35 | Diseño Gráfico y Publicidad |
| PC_DP_3  | Laptop  | 192.168.3.36 | Diseño Gráfico y Publicidad |
| PC_DP_4  | Desktop | 192.168.3.37 | Diseño Gráfico y Publicidad |
| PC_DP_5  | Desktop | 192.168.3.38 | Diseño Gráfico y Publicidad |
| PC_DP_6  | Laptop  | 192.168.3.39 | Diseño Gráfico y Publicidad |

## Configuración de switches

Para la configuración de los dos switches, se utilizaron los siguientes comandos:

* __enable:__ ir al modo privilegiado.
* __configure terminal:__ ir al modo de configuración global.
* __hostname NuevoNombreSwitch:__ configurar el nombre de host del switch, asignándole el valor en 'NuevoNombreSwitch'.
* __enable secret NuevaContraseñaSwitch:__ configurar la contraseña de acceso al modo privilegiado, asignándole el valor en 'NuevaContraseñaSwitch'.
* __write memory:__ guardar la configuración actual en memoria.
* __exit:__ salir del modo de configuración.

## Configuración de equipos

En las siguientes imágenes se muestran algunos ejemplos de la configuración realizada a cada uno de los equipos de cómputo de los diversos departamentos de la empresa, específicamente, la configuración de la dirección IP. 

Equipo de cómputo del departamento de "Alta Dirección":
![Configuración equipo Alta Dirección](img/ConfiguracionPC1.png)

Equipo de cómputo del departamento de "Renderizado y Modelado 3D":
![Configuración equipo Renderizado y Modelado 3D](img/ConfiguracionPC2.png)

Equipo de cómputo del departamento de "Recepción y Administración":
![Configuración equipo Recepción y Administración](img/ConfiguracionPC3.png)

Equipo de cómputo del departamento de "Arquitectura y Urbanismo":
![Configuración equipo Arquitectura y Urbanismo](img/ConfiguracionPC4.png)

Equipo de cómputo del departamento de "Diseño Gráfico y Publicidad":
![Configuración equipo Diseño Gráfico y Publicidad](img/ConfiguracionPC5.png)

## Ping entre hosts

En las siguientes imágenes se muestran algunos ejemplos de pings realizados entre hosts de distintas áreas, esto con el fin de comprobar la existencia de comunicación entre los equipos.

Ping entre equipo de "Alta Dirección" y "Renderizado y Modelado 3D":
![Ping entre equipo Alta Dirección y Renderizado y Modelado 3D](img/Ping1.png)

Ping entre equipo de "Renderizado y Modelado 3D" y "Recepción y Administración":
![Ping entre equipo Renderizado y Modelado 3D y Recepción y Administración](img/Ping2.png)

Ping entre equipo de "Recepción y Administración" y "Arquitectura y Urbanismo":
![Ping entre equipo Recepción y Administración y Arquitectura y Urbanismo](img/Ping3.png)

Ping entre equipo de "Arquitectura y Urbanismo" y de "Diseño Gráfico y Publicidad":
![Ping entre equipo Arquitectura y Urbanismo y Diseño Gráfico y Publicidad](img/Ping4.png)

Ping entre equipo de "Diseño Gráfico y Publicidad" y de "Alta Dirección":
![Ping entre equipo Diseño Gráfico y Publicidad y Alta Dirección](img/Ping5.png)

## Demostración de captura de un paquete ARP

En la imagen se muestra la captura de un paquete ARP utilizando el modo simulación de Packet Tracer:

![Captura de un paquete ARP](img/ARP1.png)

## Demostración de captura de un paquete ICMP

En la imagen se muestra la captura de un paquete ICMP haciendo uso del modo simulación de Packet Tracer:

![Captura de un paquete ICMP](img/ICMP1.png)