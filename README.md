# **Práctica 2 - Redes 1**

## Configuración de Routers

* R1

<div align="center">
    <img src="img/img1.png" width="500">
</div>

* R2

<div align="center">
    <img src="img/img2.png" width="500">
</div>

* R6

<div align="center">
    <img src="img/img4.png" width="500">
</div>

## Configuración de Switches

* SW1

<div align="center">
    <img src="img/img5.png" width="500">
</div>

* SW3

<div align="center">
    <img src="img/img6.png" width="500">
</div>

## Configuración de VPC

* VPC11

<div align="center">
    <img src="img/img7.png" width="500">
</div>

* VPC14

<div align="center">
    <img src="img/img8.png" width="500">
</div>

| **Tarea**                                      | **Comandos Utilizados**                                                                                                                                   |
|------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Creación de Ruta Estática**                  | `ip route <network> <subnet mask> <next-hop>` <br> Ejemplo: `ip route 102.168.0.0 255.255.255.0 102.168.1.1`                                               |
| **Creación de PortChannel con PAGP**           | - `interface range <interfaces>` <br> - `channel-group <number> mode desirable` <br> - `interface port-channel <number> switchport mode trunk`             |
| **Creación de PortChannel con LACP**           | - `interface range <interfaces>` <br> - `channel-group <number> mode active` <br> - `interface port-channel <number> switchport mode trunk`                |
| **Creación de IP Virtual con HSRP**            | - `standby <group> ip <virtual ip>` <br> - `standby <group> priority <priority>` <br> - `standby <group> preempt` <br> Ejemplo: `standby 1 ip 102.168.0.1` |
| **Configuración de VPC**                       | - `ip route <network> <subnet mask> <next-hop>` <br> Ejemplo: `ip route 10.0.0.0 255.255.255.252 10.0.0.2`                                                 |

| **Verificación de Funcionamiento**             | **Comandos de Verificación**                                                                                                                              |
|------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Verificar rutas estáticas**                  | `show ip route`                                                                                                                                           |
| **Verificar estado de PortChannel con PAGP**   | `show etherchannel summary` <br> `show etherchannel port-channel`                                                                                          |
| **Verificar estado de PortChannel con LACP**   | `show etherchannel summary` <br> `show etherchannel port-channel`                                                                                          |
| **Verificar estado de HSRP**                   | `show standby brief`                                                                                                                                      |
| **Verificar conectividad VPC**                 | `ping -t <IP destino>`                                                                                                                                       |
