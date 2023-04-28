
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

![](https://github.com/zazi479/Flask-Python/blob/e139a3b441d5f3641006c4e0f014fea0abd64fea/foto1.png)
    
4.  Una vez completada la creación de su entorno virtual, ejecute Terminal: Crear nueva terminal ( Ctrl+Shift+` )) desde la Paleta de comandos, que crea una terminal y activa automáticamente el entorno virtual ejecutando su secuencia de comandos de activación.

**Nota** : en Windows, si su tipo de terminal predeterminado es PowerShell, es posible que vea un error que indica que no puede ejecutar enable.ps1 porque la ejecución de secuencias de comandos está deshabilitada en el sistema. El error proporciona un enlace para obtener información sobre cómo permitir scripts. De lo contrario, use Terminal: seleccione Shell predeterminado para establecer "Símbolo del sistema" o "Git Bash" como predeterminado.

5.  Instale Flask en el entorno virtual ejecutando el siguiente comando en VS Code Terminal:

```
python -m pip install flask
```


![](https://github.com/zazi479/Flask-Python/blob/a013533501f504b6faebdb5212853517956b0626/foto3.png)

Ahora tiene un entorno autónomo listo para escribir código Flask. VS Code activa el entorno automáticamente cuando usa Terminal: Create New Terminal . Si abre un símbolo del sistema o terminal independiente, active el entorno ejecutando source .venv/bin/activate(Linux/macOS) o .venv\Scripts\Activate.ps1(Windows). Sabrá que el entorno está activado cuando el símbolo del sistema muestra (.venv) al principio.

1. Cree y ejecute una aplicación Flask mínima
    En VS Code, cree un archivo nuevo en la carpeta de su proyecto con el nombre app.pyArchivo > Nuevo en el menú, presione Ctrl+N o use el ícono de archivo nuevo en       la Vista del explorador (que se muestra a continuación).

    ![](https://github.com/zazi479/Flask-Python/blob/ba6fad39d9c1096f329d3317f621f77877728f5c/foto2.png)


2. En app.py, agregue código para importar Flask y cree una instancia del objeto Flask. Si escribe el código a continuación (en lugar de usar copiar y pegar), puede      observar el IntelliSense y las funciones de autocompletado de VS Code :

![](https://github.com/zazi479/Flask-Python/blob/b181e98dd1ccc26982a9b673a4aefee08441a554/foto4.png)

3.  También en app.py, agregue una función que devuelva contenido, en este caso una cadena simple, y use el app.routedecorador de Flask para asignar la ruta URL /a esa     función:

![](https://github.com/zazi479/Flask-Python/blob/b181e98dd1ccc26982a9b673a4aefee08441a554/foto5.png)

4.  Guarde el app.pyarchivo ( Ctrl+S ).

5.  En la Terminal integrada, ejecute la aplicación ingresando python -m flask run, que ejecuta el servidor de desarrollo de Flask. El servidor de desarrollo busca         app.pypor defecto. Cuando ejecuta Flask, debería ver un resultado similar al siguiente:

Si ve un error que indica que no se puede encontrar el módulo Flask, asegúrese de haberlo ejecutado python -m pip install flasken su entorno virtual como se describe al final de la sección anterior.

Además, si desea ejecutar el servidor de desarrollo en una dirección IP o puerto diferente, use los argumentos de línea de comandos de host y puerto, como con --host=0.0.0.0 --port=80.

6.  Para abrir su navegador predeterminado en la página renderizada, presione Ctrl y haga clic en la http://127.0.0.1:5000/URL en la terminal.

![](https://github.com/zazi479/Flask-Python/blob/b181e98dd1ccc26982a9b673a4aefee08441a554/foto6.png)

7.  Observe que cuando visita una URL como /, aparece un mensaje en la terminal de depuración que muestra la solicitud HTTP:

![](https://github.com/zazi479/Flask-Python/blob/2261989c997423bbc0f7ed06a2c1ba6f95c7c9dd/foto7.png)

8.  Detenga la aplicación usando Ctrl+C en la terminal.


# Ejecute la aplicación en el depurador

La depuración le brinda la oportunidad de pausar un programa en ejecución en una línea de código en particular. Cuando un programa está en pausa, puede examinar las variables, ejecutar código en el panel de la consola de depuración y aprovechar las funciones descritas en Depuración . La ejecución del depurador también guarda automáticamente los archivos modificados antes de que comience la sesión de depuración.

1.  Reemplace el contenido de app.pycon el siguiente código, que agrega una segunda ruta y función que puede recorrer paso a paso en el depurador:

![](https://github.com/zazi479/Flask-Python/blob/9f93e1cc82692fe733b4cb0bcffd98b86540a70f/foto8.png)

El decorador utilizado para la nueva ruta URL, /hello/<name>define un punto final /hola/ que puede aceptar cualquier valor adicional. El identificador dentro <y >en la ruta define una variable que se pasa a la función y se puede usar en su código.

Las rutas URL distinguen entre mayúsculas y minúsculas. Por ejemplo, la ruta /hello/<name>es distinta de /Hello/<name>. Si desea que la misma función maneje ambos, use decoradores para cada variante.
    
2.  Establezca un punto de interrupción en la primera línea de código de la hello_therefunción ( now = datetime.now()) realizando cualquiera de las siguientes             acciones:
    
    -   Con el cursor en esa línea, presione F9.
    -   Haga clic directamente en el margen a la izquierda del número de línea (aparece un punto rojo desvaído al pasar el cursor por allí).
    
        El punto de interrupción aparece como un punto rojo en el margen izquierdo:
    
![](https://github.com/zazi479/Flask-Python/blob/9faad195566ea5a7436044c7e88314630cf5cead/foto9.png)
    
 3.  Cambie a la vista Ejecutar y depurar en VS Code (usando la barra de actividad del lado izquierdo o Ctrl+Shift+D ). Es posible que vea el mensaje "Para                 personalizar Ejecutar y Depurar, cree un archivo launch.json". Esto significa que aún no tiene un launch.jsonarchivo que contenga configuraciones de                   depuración. VS Code puede crearlo por usted si hace clic en el vínculo Crear un archivo launch.json : .
    
![](https://github.com/zazi479/Flask-Python/blob/af0a3ba0aac873b0858ea0dbe6fc2fd0bf420647/foto10.png)

4.  Debe de aparecer el archivo con este contenido:
    
![](https://github.com/zazi479/Flask-Python/blob/03d5197dd281f62f7ea12180b1a473bc51853304/foto11.png)
    
5.  Guardar launch.json( Ctrl+S ). En la lista desplegable de configuración de depuración, seleccione Python: Configuración de matraz.

![](![image](https://user-images.githubusercontent.com/114684585/235234697-50b65ce3-cb9d-425f-85b1-c24dad5199d1.png)
    
    
   Observe que la barra de estado cambia de color para indicar la depuración:
    
 ![](https://github.com/zazi479/Flask-Python/blob/0a6e74433da014a1ae07ff09cad039454f93166b/fooo1.png)
    
 En mi caso no funciona.
    
6.  Una barra de herramientas de depuración (que se muestra a continuación) también aparece en VS Code que contiene comandos en el siguiente orden: Pausa (o Continuar,     F5 ), Pasar por encima ( F10 ), Entrar ( F11 ), Salir ( Shift+F11 ), Reiniciar ( Ctrl +Mayús+F5 ) y Detener ( Mayús+F5 ). Consulte Depuración de VS Code para           obtener una descripción de cada comando.

 ![](https://github.com/zazi479/Flask-Python/blob/f9c0eb17a1a8c6359bb7e3659b1b77852e572293/foto12.png)
    
    
7.  La salida aparece en un terminal de "Consola de depuración de Python". Ctrl+clic en el http://127.0.0.1:5000/enlace en ese terminal para abrir un navegador a esa       URL. En la barra de direcciones del navegador, navegue hasta http://127.0.0.1:5000/hello/VSCode. Antes de que se muestre la página, VS Code detiene el programa en     el punto de interrupción que estableció. La pequeña flecha amarilla en el punto de interrupción indica que es la siguiente línea de código que se ejecutará.
    
Mota: es como deberia de aparecer.  
    
 ![](https://github.com/zazi479/Flask-Python/blob/0a6e74433da014a1ae07ff09cad039454f93166b/fotooo1.png)

9.  Use Step Over para ejecutar la now = datetime.now()declaración.

10. En el lado izquierdo de la ventana de VS Code, verá un panel Variables que muestra variables locales, como now, así como argumentos, como name. Debajo hay paneles      para Watch , Call Stack y Breakpoints (consulte Depuración de VS Code para obtener más detalles). En la sección Locales , intente expandir diferentes valores.          También puede hacer doble clic en los valores (o usar F2 ) para modificarlos. Sin embargo, cambiar variables como now, puede romper el programa. Los                    desarrolladores suelen hacer cambios solo para corregir los valores cuando el código no produjo el valor correcto para empezar.  
    
    
![image](https://user-images.githubusercontent.com/114684585/235236306-61989363-17e8-4b2c-8b22-a4e309b21073.png)
    
    
11. Avance por algunas líneas más de código, si lo desea, luego seleccione Continuar ( F5 ) para dejar que el programa se ejecute. La ventana del navegador muestra el      resultado:
    
 ![](https://github.com/zazi479/Flask-Python/blob/d08ce91659dbb0bfc15a897be708ed192a999140/foto13.png)
    
    
    
   

    
