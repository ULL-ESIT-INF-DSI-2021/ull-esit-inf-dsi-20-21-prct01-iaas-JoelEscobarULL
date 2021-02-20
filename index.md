- # *Asignatura | Desarrollo de Sistemas Informáticos*
- #  *Institución | Universidad de La Laguna*
- # *Autor | Joel Francisco Escobar Socas*
  - # contacto | alu0101130408@ull.edu.es 

# __Práctica 01: Configuración de la máquina virtual en el IaaS__

- ## Introducción
En esta práctica inicial configuraremos nuestra máquina virtual en el servicio IaaS de la Universidad de la Laguna y también instalaremos las herramientas necesarias para comenzar a trabajar en las futuras prácticas que llevaremos a cabo en la asignatura.
- ## Desarrollo
  - ### Herramientas previas
       Antes de comenzar con la configuración de la máquina virtual, tenemos que tener una cuenta de GitHub creada, en mi caso ya tenía una de asignaturas                 anteriores.
  - ### Configuración
      Vamos a comenzar la configuración, pero antes para poder iniciar la máquina virtual dentro del portal del Iaas necesitamos establecer una conexión VPN con la       Universidad de la laguna, en el siguiente enlace nos muestra como:
      
    - [Instalación de la VPN de la Universidad de la Laguna](https://www.ull.es/servicios/stic/2020/12/01/servicio-de-vpn-de-la-ull/).
    
     Una vez instalada la VPN de la Ull siguiendo los pasos que se encuentras especificiados en el link anterior, comenzaremos acceder al [servicio IaaS](https://iaas.ull.es/ovirt-engine/) y introducimos nuestros datos de la cuenta asociada a la ULL. una vez accedemos al portal, nos aparecerá todas las maquinas que tengamos creadas, en este caso encenderemos la maquina que aparecerá como DSI. Sabrá que lo anterior ha sucedido debido a que su máquina pasará a tener un número como sufijo, en mi ejemplo DSI-22.
     
     Haga clic en el nombre de su máquina virtual y, en la parte derecha de la interfaz, donde se indica Interfaces de red, podrá conocer la IP asignada a la interfaz de su máquina. Conociendo dicha IP, ya podrá conectarse por SSH a su máquina. Es importante recordar que siempre tiene que estar conectado a la VPN de la ULL para trabajar con una máquina virtual del IaaS. Para conectarse por SSH a su máquina virtual, abra una terminal y escriba 
     ```Bash
     ssh usuario@10.6.XXX.XXX
     ```
     siendo 'XXX' la dirección IP que se le ha asignado.
     
     A continuación introducimos "yes" y lo que haremos será introducir la contraseña, en este caso será 'usuario' y nos pedirá otra vez la contraseña y luego la nueva contraseña, que será la que remplazaremos asi que deberiamos anotarla bien. Tener en cuenta que tendrá que volver a iniciar una conexión SSH con su máquina, pero esta vez deberá usar su nueva contraseña para acceder, para cerrar la conexión anterior basta con introducir "exit" en la sesión iniciada.
     
     Ahora lo que haremos será modificar el nombre de host de la máquina, buscaremos modificar los ficheros de configuración ejecutando los siguientes comandos:
    ``` Bash
     $ cat /etc/hostname
     $ sudo vi /etc/hostname
     $ cat /etc/hostname
    ```
    Se deberá de visualizar al final algo así:
    (Imagen con el archivo de configuración)
    
    En mi caso llamé a mi máquina DSI22, también podemos modificar el fichero de configuración de la siguiente forma:
   ```
   $ sudo vi /etc/hosts
   $ cat /etc/hosts
   ```
    Quedaría de la siguiente forma:
    (Imagen de HOST)
    
    En este caso, he cambiado el antiguo nombre de host ubuntu, por el nombre de host iaas-dsi22. Antes de proceder a reiniciar la máquina virtual para que todos   los cambios tengan efecto, actualice el software de la misma, bastará con las siguientes líneas:
  ```
  $ sudo apt update
  $ sudo apt upgrade
  ```
    Y ahora procedemos a reiniciar la máquina, solo necesitará usar:
    ```
    $ sudo reboot
    ```
    En lo que la máquina se reincia, podemos hacer que para conectarnos en la máquina no introduzcamos la IP, para hacer esto bastará con editar el fichero `/etc/hosts` en nuestra máquina local (nuestro ordenador personal, no la máquina virtual de la asignatura) y asignarle la dirección ip de nuestra maquina virtual 
  ```
  $ cat /etc/hosts
  $ sudo vi /etc/hosts
  $ cat /etc/hosts
  ```
  Se debería poder visualizar algo así:
  (imagen del fichero local)
  
 En caso de no haberlo hecho, en nuestra propia máquina configuraremos la infraestructura de clave pública-privada, para ver si tenemos el fichero generado ejecutaremos el comando `cat .ssh/id_rsa.pub` si no lo tenemos, bastará con hacer:
 ```
 $ ssh-keygen
 ```
 Y se nos abrirá un script que nos pedirá las opciones de configuración para generar la clave, bastará las de defecto, para ello, simplemente le damos a enter sin escribir nada, es importante que no se introduzca ninguna passphrase asociada al par de claves pública-privada.
 y ahora ejecutamos el siguiente comando para copiar la clave que acabamos de generar desde nuestra máquina a la máquina virtual
  ```
  $ ssh-copy-id usuario@iaas-dsi22
  ```
  Vamos a probar lo que acabamos de hacer, entonces ejecutamos nuevamente `exit` para cerrar sesión y bastará con ejecutar el ssh solo con el nombre del host de la máquina, Acuerdese de cambiar el nombre del host, al que haya usted introducido, en mi caso le puse iaas-dsi22  
  ``` 
  $ ssh usuario@iaas-dsi22
  ```
  Si tampoco quisiera utilizar el nombre de usuario (usuario) de la máquina virtual a la hora de conectarse vía SSH, puede configurar el fichero ` ~/.ssh/config` en su máquina local
  ```
  $ touch ~/.ssh/config
  $ vi ~/.ssh/config 
  $ cat ~/.ssh/config 
  ``` 
  Deberá quedar algo como:
  (imagen con el config de la maquina virtual)
  
  También deberiamos generar las claves necesarias como hicimos con anterioridad en la máquina local:
  ```
  $ ssh-keygen 
  ```
  nos preguntará donde introducimos la clave especificaremos la siguiente ruta: `/home/usuario/.ssh/id_rsa`. Y pulsamos enter en la siguiente pregunta para hacer que obtenga el passphrase por defecto. Ahora si queremos ver la clave bastará con hacer:
  ```
  $ cat .ssh/id_rsa.pub 
  ```
  En mi caso se ve así:
  (Imagen de la clave )
  
  Ahora se debería poder iniciar una conexión SSHsolo con el nombre de la máquina virtual, por ejemplo `ssh iaas-dsi22`.
 
  - ### Instalación de Git y Node.js
  
- ###  Dificultades Encontradas

- ## Conclusión

- ## Bibliografia
