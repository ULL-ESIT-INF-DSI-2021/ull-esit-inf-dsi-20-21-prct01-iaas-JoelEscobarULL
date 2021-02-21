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
       
       ![GitHub_profile](https://github.com/ULL-ESIT-INF-DSI-2021/ull-esit-inf-dsi-20-21-prct01-iaas-JoelEscobarULL/blob/main/P1/gituhb%20inicio.png)
       
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
     
      
  - ### Instalación de Git y Node.js
    - #### Git

 
    - #### Node.js


  - ###  Dificultades Encontradas

- ## Conclusión

- ## Bibliografia
  - [Guión de la práctica 1 de la asignatura de Desarrollo de Sistemas Informaticos](https://ull-esit-inf-dsi-2021.github.io/prct01-iaas/).
  - [Plataforma del IaaS de la ULL](https://iaas.ull.es).
  - [Introducción a MarkDown](https://guides.github.com/features/mastering-markdown/).
  - [Introduccion a Github Pages](https://docs.github.com/en/github/working-with-github-pages).
  - [Script de .git-prompt](https://github.com/git/git/blob/master/contrib/completion/git-prompt.sh).
  - [Documentación de configuración de la VPN de la ULL](https://www.ull.es/servicios/stic/2020/12/01/servicio-de-vpn-de-la-ull/).
  - [Guia de configuración de git](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Configurando-Git-por-primera-vez).
  - [Node versión Manager](https://github.com/nvm-sh/nvm).
  - [Node Package Manager](https://www.npmjs.com/).
  - [Introducción a Github](https://lab.github.com/githubtraining/introduction-to-github).
  - [Información sobre Jeckyll](https://jekyllrb.com/).
  - [Página de la Universidad de la Laguna](https://www.ull.es/)
  


