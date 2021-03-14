# <center>  MANUAL VPN EN GCP </center>

## INSTRUCCIONES
<ol> 
    <li><a href="#info">ANTES DE EMPEZA
        <ol>
            <a href="#info1"><li>SOFWARE NECESARIO</li></a>
            <a href="#info2"><li>GOOGLE CLUD PLATFORM </li></a>
        </ol>
    <li><a href="#firewall"> REGLAS DE FIREWALL </a> 
        <ol>
            <a href="#firewall1"><li>CARGAR NUEVA REGLA DE FIRE WALL</li></a>
            <a href="#firewall2"><li>REGLAS DE ENTRADA </li></a>
            <a href="#firewall3"><li>REGLAS DE SALIDA </li></a>
        </ol>
    </li>
    <li><a href="#mv"> MÁQUINA VIRTUAL (GCP)</a> 
        <ol>
            <a href="#firewall"><li>REGLAS DE ENTRADA </li></a>
            <a href="#firewall"><li>REGLAS DE SALIDA </li></a>
        </ol>
    </li>
    <li><a href="#vpn"> CONFIGURACIÓN VPN </a> 
        <ol>
            <a href="#firewall"><li>REGLAS DE ENTRADA </li></a>
            <a href="#firewall"><li>REGLAS DE SALIDA </li></a>
        </ol>
    </li>
</ol>



## <div id="info"> 1. ANTES DE EMPEZA </div>
### <div id="info1"> 1.1 SOFTWARE NECESARIO </div>
Para poder realizar la conexion de los host físicos es ncesario de un cliente VPN, para fines de esta práctica se utilizó el software OpenVPN Connect
El cuál puede se obtenido de su página  

> https://openvpn.net/download-open-vpn/

OpenVPN Connect es conpatible con:
- Windws
- Linux
- macOS
- Android
- Iphon

### <div id="info2"> 1.2 GOOGLE CLUD PLATFORM </div>
Es necesario de una cuenta activa en Google para poder registrarse en Google Cloud Platform. Google Cloud Platformm ofrece una capa gratuita, tras haber registrado una targeta de débito o crédito, la cual ofrece $300 como crédito y 3 meses de tiempo límite para ocupar la capa gratuita.  
El servidor VPN se levantó sobre la capa gratuita que proporciona Google Cloud Platform.  

> https://cloud.google.com/



## <div id="firewall"> 2. REGLAS DE FIREWALL </div>
Buscaremos al apartado de 'Red de VPC' -> 'Firewall' para agregar las nuevas reglas.

![firewall_1](./Imagenes/vpn_gcp/firewall_1.png)

Selecionaremos la opción de 'CARGAR REGLA DE FIREWAL'.  
Usaremos esta opción para cargar las reglas de entrada y salida.  

![firewall_2](./Imagenes/vpn_gcp/firewall_2.png)

### <div id="firewall"> 2.1 REGLAS DE ENTRADA</div>
Ingresaremos un nuevo nombre para nuestra nueva regla (para fines de esta práctica se escogio el nombre de 'all-in' pero esta puede ser cambiada a conbeniencia del creador de la nueva regla). Además podemos agregar una descripción de nuestra nueva regla, este campo es opcional.  

![firewall_3](./Imagenes/vpn_gcp/firewall_3.png)

A fines de esta práctica dejaremos de las opciones de 'Registros', 'Red' y 'Prioridad' con los valores que vienen por defecto.  

![firewall_4](./Imagenes/vpn_gcp/firewall_4.png)

Ahora seleccionaremos como 'Dirección de tráfico'->'Entrada' y 'Acción en caso de coincidencia'->'Permitir'  

![firewall_5](./Imagenes/vpn_gcp/firewall_5.png)

En la opción 'Destinos'->'Etiquetas de destino especificadas' con el fin de aplicar estas reglas a la red de las Máquinas Virtuales únicamente que tengan en sus etiquetas de red el la etiquta definida en 'Etiquetas de destino' (para fines de esta práctica se eligio el nombre de 'openvpn'), es importante que tanto las reglas de entrada y salida tengan la misma etiqueta para que ambas reglas sean aplicadas en la red de la Máquina Virtual.  


![firewall_6](./Imagenes/vpn_gcp/firewall_6.png)

### <div id="mv"> 2.2 REGLAS DE SALIDA  </div>
Ingresaremos un nuevo nombre para nuestra nueva regla (para fines de esta práctica se escogio el nombre de 'all-out' pero esta puede ser cambiada a conbeniencia del creador de la nueva regla). Además podemos agregar una descripción de nuestra nueva regla, este campo es opcional.  

![firewall_3](./Imagenes/vpn_gcp/firewall_.png)

A fines de esta práctica dejaremos de las opciones de 'Registros', 'Red' y 'Prioridad' con los valores que vienen por defecto.  

![firewall_4](./Imagenes/vpn_gcp/firewall_4.png)

Ahora seleccionaremos como 'Dirección de tráfico'->'Salida' y 'Acción en caso de coincidencia'->'Permitir'  

![firewall_5](./Imagenes/vpn_gcp/firewall_.png)

## <div id="mv"> 3. MÁQUINA VIRTUAL (GCP)  </div>

## <div id="vpn"> 4. INSTALACIÓN DE VPN </div>
