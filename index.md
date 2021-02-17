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
     
     A continuación pulsaremos sobre "yes" y lo que haremos será introducir la contraseña, en este caso será 'usuario' y nos pedirá otra vez la contraseña y luego la nueva contraseña, que será la que remplazaremos asi que deberiamos anotarla bien.
     
 - ###  Dificultades Encontradas

 - ### Conclusión

 - ### Bibliografia
