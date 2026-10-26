# portafolio-ccna2
proyecto final
# h1 Encabezado

  ## Formato
  
  **Esto es un texto en negrita** y __esto también lo es__
  *Esto es un texto en cursiva* y _esto también lo es_

  ## Listas
  
  + Puedes crear listas con los símbolos +, -, or *
  + Y también sublistas agreganndo 2 espacios:
    - Cada marcador creará un nuevo elemento:
      * Cuenta con mi espada
      + Y con mi arco
      - Y con mi hacha
  + No es tan difícil


enable
configure terminal
hostname R-Core

interface GigabitEthernet0/0
 no shutdown
 exit

interface GigabitEthernet0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.254 255.255.255.0
 exit

interface GigabitEthernet0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.254 255.255.255.0
 exit

interface GigabitEthernet0/0.30
 encapsulation dot1Q 30
 ip address 192.168.30.254 255.255.255.0
 exit

interface GigabitEthernet0/0.99
 encapsulation dot1Q 99
 ip address 192.168.99.254 255.255.255.0
 exit

interface GigabitEthernet0/0.111
 encapsulation dot1Q 111 native
 exit

enable
configure terminal
hostname SW-Core

vlan 10
 name ADMINISTRACION
vlan 20
 name LABORATORIOS
vlan 30
 name DIRECCION
vlan 99
 name GESTION
vlan 111
 name NATIVA

interface range Fa0/23 - 24, Gig0/1
 switchport mode trunk
 switchport trunk native vlan 111
 no shutdown
 exit

interface Fa0/9
 switchport mode access
 switchport access vlan 99
 no shutdown
 exit

 enable
configure terminal
hostname SW-Lab1  *(o SW-Lab2 según corresponda)*

vlan 10
 name ADMINISTRACION
vlan 20
 name LABORATORIOS
vlan 30
 name DIRECCION
vlan 99
 name GESTION
vlan 111
 name NATIVA

interface range Fa0/1 - 3
 switchport mode access
 switchport access vlan 10
 no shutdown
 exit

interface range Fa0/4 - 6
 switchport mode access
 switchport access vlan 20
 no shutdown
 exit

interface Fa0/7
 switchport mode access
 switchport access vlan 30
 no shutdown
 exit

interface Fa0/24  *(o el puerto trunk que use)*
 switchport mode trunk
 switchport trunk native vlan 111
 no shutdown
 exit

 
