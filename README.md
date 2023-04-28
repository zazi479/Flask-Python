
# Flask Tutorial in Visual Studio Code

## Reequisitos previos

Para completar con éxito este tutorial de Flask, debe hacer lo siguiente (que son los mismos pasos que en el tutorial general de Python ):

1. Instala la extensión de Python. 
2. Instale una versión de Python 3 (para la cual se escribió este tutorial). Las opciones incluyen:
    - (Todos los sistemas operativos) Una descarga desde python.org ; por lo general, use el botón Descargar que aparece primero en la página.
    - (Linux) La instalación integrada de Python 3 funciona bien, pero para instalar otros paquetes de Python debe ejecutarlos sudo apt install python3-pipen la terminal.
      (macOS) Una instalación a través de Homebrew en macOS usando brew install python3.
    - (Todos los sistemas operativos) Una descarga de Anaconda (para fines de ciencia de datos).
3. En Windows, asegúrese de que la ubicación de su intérprete de Python esté incluida en su variable de entorno PATH. Puede verificar la ubicación ejecutando pathen el      símbolo del sistema. Si la carpeta del intérprete de Python no está incluida, abra la Configuración de Windows, busque "entorno", seleccione Editar variables de          entorno para su cuenta , luego edite la variable Ruta para incluir esa carpeta.

# Crear un entorno de proyecto para el tutorial de Flask

En esta sección, creará un entorno virtual en el que se instalará Flask. El uso de un entorno virtual evita la instalación de Flask en un entorno global de Python y le brinda un control exacto sobre las bibliotecas utilizadas en una aplicación.

En su sistema de archivos, cree una carpeta para este tutorial, como hello_flask.

Abra esta carpeta en VS Code navegando a la carpeta en un terminal y ejecutando code ., o ejecutando VS Code y usando el comando Archivo > Abrir carpeta .

En VS Code, abra la Paleta de comandos ( Ver > Paleta de comandos o ( Ctrl+Shift+P )). Luego seleccione el comando Python: Create Environment para crear un entorno virtual en su espacio de trabajo. Seleccione venvy luego el entorno de Python que desea usar para crearlo.

!()[https://github.com/zazi479/Flask-Python/blob/e139a3b441d5f3641006c4e0f014fea0abd64fea/foto1.png]
