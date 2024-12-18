# Plantilla_IEEE_gitlatexdiff
Esta es una plantilla en LaTeX para la escritura de artículos siguiendo las recomendaciones de la IEEE. 

Además se proporcionan algunas instrucciones básicas para su implementación con el sistema de gestión de versiones Git para el control de cambios entre distintas versiones lo que facilita su uso para revisiones en equipo.


# Sistema de control de versiones para archivos LaTeX colaborativos 

El siguiente manual describe el proceso para la instalación y el uso básico de LaTeX en conjunto con Git y GitHub para el manejo de control de versiones. 
Con esta metodología de trabajo, múltiples usuarios pueden contribuir a través de commits al desarrollo de un archivo y los cambios se pueden rastrear a través del sistema de control de versiones git. Además, es posible generar documentos identificando con colores los cambios entre distintas versiones a través de la implementación de git-latexdiff. 

Paso 1: Descarga el Instalador de Git

1.	Abre tu navegador web y visita el sitio oficial de Git: https://git-scm.com/
2.	Haz clic en el botón Download for Windows. Esto descargará el archivo ejecutable más reciente para tu versión de Windows.
   
Paso 2: Ejecuta el Instalador

1.	Ve a la carpeta donde descargaste el instalador (usualmente Descargas) y haz doble clic en el archivo ejecutable (Git-x.x.x-64-bit.exe o similar).
2.	Si el sistema solicita permisos, haz clic en Sí para continuar.
   
Paso 4: Completa la Instalación

1.	Haz clic en Install y espera a que finalice.
2.	Una vez instalado, puedes desmarcar la opción "View Release Notes" y hacer clic en Finish.
   
Paso 5: Verifica la Instalación

1.	Abre Git Bash (búscalo en el menú Inicio).
2.	Escribe el siguiente comando para verificar la versión instalada:
    git --version
  	Deberás recibir una respuesta similar a la siguiente, si este no es el caso verifica la instalación.
    git version x.x.x
  	
Paso 6: Configura Git

1.	Configura tu nombre de usuario:
    git config --global user.name "TuNombre"
2.	Configura tu correo electrónico:
    git config --global user.email "tuemail@ejemplo.com"
3.	Verifica la configuración:
    git config --list
  	
Paso 7: Instalar Perl

git-latexdiff depende de Perl, por lo que necesitas instalarlo:

1.	Descarga e instala Strawberry Perl, que incluye Perl y herramientas de desarrollo https://strawberryperl.com/
2.	Durante la instalación, asegúrate de que el instalador agrega Perl al PATH del sistema.
3.	Verifica la instalación ejecutando:
    perl –version
  	
Paso 8: Instalar LaTeX, latexdiff y git-latexdiff

git-latexdiff requiere que tengas un sistema LaTeX para procesar los archivos. Instala una distribución de LaTeX:

1.	Instala MiKTeX https://miktex.org/
2.	Instala latexdiff y git-latexdiff desde el administrador de paquetes de MikTeX
 
![image](https://github.com/user-attachments/assets/7b4ee30d-4bcb-4979-ac42-de7868df326a)


3.   Si hay un problema para instalar git-latexdiff desde el administrador de paquetes de MikTeX puedes instalarlo manualmente desde https://gitlab.com/git-latexdiff/git-latexdiff clona el repositorio o descarga el repositorio como archivo zip y después de descomprimirlo ejecutar el archivo windows_install.cmd
4.   Verifica la Instalación
     Abre una terminal Git Bash y ejecuta
     git-latexdiff --help
     Deberías ver la lista de opciones disponibles para git-latexdiff.

Paso 9: Instala un editor de LaTeX

Para este paso se recomiendan dos opciones Visual Studio Code https://code.visualstudio.com/ o TeXstudio https://www.texstudio.org/

1.  Para instalar TeXstudio se necesita descargar el instalador y seguir las instrucciones. TeXstudio está optimizado para trabajar con archivos .tex por lo que no se requiere alguna configuración adicional. 

2.  Para instalar Visual Studio Code se recomiendan instalar las siguientes extensiones una vez instalado el programa principal:
    LaText language support 
    LaTeX Snippets 
    LaTeX Utilities 
    LaTeX Workshop
    Latex-formatter
    Unicode Latex 
    Adicional Material Icon Theme 

Paso 10: Comenzar con el proyecto de LaTeX

Crea un nuevo directorio con un archivo .tex (se recomienda descargar los archivos de este repositorio para familiarizarse con el proceso). Además hay muchos recursos para familiarizarse con LaTeX.

Paso 11: Usar git en el proyecto de LaTeX

Se sugiere estudiar los conceptos básicos del sistema de control de versiones git https://git-scm.com/
Para hacer uso de git se require abrir una terminal ya sea en VSC o en TeXstudio y seguir los siguientes comandos básicos dependiendo la necesidad. 

1.  Inicializar git
    git init
2.  Ver estado de los cambios en el repositorio
    git status
3.  Seguimiento y preparación de los cambios
    git add . (para todos los cambios en el repositorio)
4.  Realizar commits
    git commit -m "Mensaje del commit"
5.  Ver historial de los commits
    git log

Paso 12: Generar un documento con los cambios resaltados usando git-latexdiff

El documento con los cambios se puede generar a partir de dos commits cualquiera. Para esto se necesitan los id de dos commits cualquiera.

  git latexdiff [options] OLD [NEW]                                                  
  git latexdiff [options] OLD --
  git latexdiff [options] – OLD

Por ejemplo: 

git latexdiff --main LaTeX_Git_IEEE_Paper_Template.tex --output git-latexdiff.pdf f23f9e0... ac7357...

Si el comando genera un error debido a las figuras se puede usar la siguiente versión:

git latexdiff --whole-tree --latexmk --ignore-latex-errors --output git-latexdiff.pdf f23f9e0... ac7357...

Paso 13: El repositorio se puede subir a GitHub y darle acceso a otros usuarios para ver sus contribuciones y llevar un control de las diversas versiones que se van generando. 
 


