
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
    
    
#   Usar una plantilla para representar una página
    
La aplicación que ha creado hasta ahora en este tutorial genera solo páginas web de texto sin formato a partir del código de Python. Aunque es posible generar HTML directamente en el código, los desarrolladores evitan esta práctica porque abre la aplicación a ataques de secuencias de comandos entre sitios (XSS) .
    
    
Una práctica mucho mejor es mantener HTML fuera de su código por completo mediante el uso de plantillas , de modo que su código se preocupe solo por los valores de los datos y no por la representación.
    
    
Una plantilla es un archivo HTML que contiene marcadores de posición para los valores que proporciona el código en tiempo de ejecución. El motor de plantillas se encarga de hacer las sustituciones al renderizar la página. El código, por lo tanto, se ocupa solo de los valores de los datos y la plantilla se ocupa solo del marcado.
    
En esta sección, crea una sola página utilizando una plantilla. En las secciones siguientes, configurará la aplicación para servir archivos estáticos y luego creara 
varias páginas para la aplicación, cada una de las cuales contiene una barra de navegación a partir de una plantilla base.

1.  Dentro de la hello_flaskcarpeta, cree una carpeta llamada templates, que es donde Flask busca las plantillas de forma predeterminada.

2.  En la templatescarpeta, cree un archivo llamado hello_there.htmlcon el contenido a continuación. Esta plantilla contiene dos marcadores de posición llamados "nombre" y "fecha", que están delimitados por pares de llaves {{y }}. Como puede ver, también puede incluir código de formato en la plantilla directamente:

    
![](https://github.com/zazi479/Flask-Python/blob/b7b63da6e1e8ebcbf0e15cf576417550df3507e2/foto14.png)
    
```
    <!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8" />
        <title>Hello, Flask</title>
    </head>
    <body>
        {%if name %}
            <strong>Hello there, {{ name }}!</strong> It's {{ date.strftime("%A, %d %B, %Y at %X") }}.
        {% else %}
            What's your name? Provide it after /hello/ in the URL.
        {% endif %}
    </body>
</html>
    
```
 

3.    En app.py, importe render_templatela función de Flask cerca de la parte superior del archivo:
    
       from flask import render_template
 
    
4.  También en app.py, modifique la hello_therefunción a usar render_templatepara cargar una plantilla y aplicar los valores con nombre (y agregue una ruta para            reconocer el caso sin nombre). render_templateasume que el primer argumento es relativo a la templatescarpeta. Por lo general, los desarrolladores nombran las          plantillas de la misma manera que las funciones que las usan, pero no se requieren nombres coincidentes porque siempre se hace referencia al nombre de archivo          exacto en su código.

```
    @app.route("/hello/")
@app.route("/hello/<name>")
def hello_there(name = None):
    return render_template(
        "hello_there.html",
        name=name,
        date=datetime.now()
    )
```
    
5.  Inicie el programa (dentro o fuera del depurador, usando Ctrl+F5 ), navegue a una URL /hola/nombre y observe los resultados.

6.  También intente navegar a una URL / hola / nombre usando un nombre como <a%20value%20that%20could%20be%20HTML>para ver el escape automático de Flask en el trabajo.     El valor de "nombre" se muestra como texto sin formato en el navegador en lugar de representar un elemento real.
    
    
    ![](https://github.com/zazi479/Flask-Python/blob/292e49be5972dd49f7290ae0aee23375c5a2e8e9/fotos%20flask/foto%2015.png)
    
# Servir archivos estáticos

Los archivos estáticos son de dos tipos. Primero están aquellos archivos como hojas de estilo a los que una plantilla de página puede hacer referencia directamente. Dichos archivos pueden vivir en cualquier carpeta de la aplicación, pero comúnmente se colocan dentro de una staticcarpeta.

El segundo tipo son aquellos que desea abordar en el código, como cuando desea implementar un punto final de API que devuelve un archivo estático. Para este propósito, el objeto Flask contiene un método integrado, send_static_fileque genera una respuesta con un archivo estático contenido dentro de la staticcarpeta de la aplicación.
    
    
# Hacer referencia a archivos estáticos en una plantilla
    
1.  En la hello_flaskcarpeta, cree una carpeta llamada static.
    
![](https://github.com/zazi479/Flask-Python/blob/9b9c9c6554c84b0db333bc887628f4280624a858/fotos%20flask/foto16.png)
    
2.  Dentro de la staticcarpeta, cree un archivo site.csscon el siguiente contenido. Después de ingresar este código, observe también el resaltado de sintaxis que           proporciona VS Code para los archivos CSS, incluida una vista previa en color:
    
```
    .message {
    font-weight: 600;
    color: blue;
}
```
    
 
3.  En templates/hello_there.html, agregue la siguiente línea antes de la </head>etiqueta, lo que crea una referencia a la hoja de estilo.3.    
 
```
<link rel="stylesheet" type="text/css" href="{{ url_for('static', filename='site.css')}}" />
   
```
    
4.  También en templates/hello_there.html, reemplace el <body>elemento de contenido con el siguiente marcado que usa el messageestilo en lugar de una <strong>etiqueta      (y también muestra un mensaje si solo usa un hola/URL sin nombre):
    
```
    {%if name %}
    <span class="message">Hello there, {{ name }}!</span> It's {{ date.strftime("%A, %d %B, %Y at %X") }}.
{% else %}
    <span class="message">What's your name? Provide it after /hello/ in the URL.</span>
{% endif %}
    
```
    
 5. Ejecute la aplicación, navegue a una URL /hola/nombre y observe que el mensaje se muestra en azul. Detenga la aplicación cuando haya terminado
    
    
![](https://github.com/zazi479/Flask-Python/blob/2903c017c1b77da3ab7b90ed103cfbf447091dd0/fotos%20flask/foto17.png)
    
 #  Servir un archivo estático desde el código
    
  1.  En la staticcarpeta, cree un archivo de datos JSON data.jsoncon el siguiente contenido (que son datos de muestra sin sentido):
    
```
    {
  "01": {
    "note": "This data is very simple because we're demonstrating only the mechanism."
  }
}
```
    
  2.  En app.py, agregue una función con la ruta /api/data que devuelva el archivo de datos estáticos usando el send_static_filemétodo:  
    
```
    @app.route("/api/data")
def get_data():
    return app.send_static_file("data.json")
```

![](https://github.com/zazi479/Flask-Python/blob/317c17fc881ad9a98dee4d89bccef297381f8f71/fotos%20flask/foto18.png)
    
 3. Ejecute la aplicación y navegue hasta el punto final /api/data para ver si se devuelve el archivo estático. Detenga la aplicación cuando haya terminado.
    
    Al introducir la URL "http://127.0.0.1:5000/api/data"  nos apaerece el siguiente mensaje:
    
 ![](https://github.com/zazi479/Flask-Python/blob/f0f4a1b38b601699196dff193bd0c44722554c2f/fotos%20flask/foto19.png)
    
    
    
#   Crear una plantilla y estilos de página base
    
    
Una plantilla de página base en Flask contiene todas las partes compartidas de un conjunto de páginas, incluidas las referencias a archivos CSS, archivos de script, etc. Las plantillas base también definen una o más etiquetas de bloque que se espera que anulen otras plantillas que amplían la base. Una etiqueta de bloque está delineada por {% block <name> %}y {% endblock %}en la plantilla base y las plantillas extendidas.

Los siguientes pasos demuestran cómo crear una plantilla base.

1.  En la templates carpeta, cree un archivo llamado layout.htmlcon el contenido a continuación, que contiene bloques llamados "título" y "contenido". Como puede ver,     el marcado define una estructura de barra de navegación simple con enlaces a las páginas Inicio, Acerca de y Contacto, que creará en una sección posterior. Cada       enlace vuelve a utilizar la etiqueta de Flask url_forpara generar un enlace en tiempo de ejecución para la ruta coincidente.
    
![](https://github.com/zazi479/Flask-Python/blob/d54009d0c7f6fc42c32b7f0d17b8f62c6169450f/fotos%20flask/foto20.png)
    
    
2.  Agregue los siguientes estilos a static/site.css, debajo del estilo de "mensaje" existente y guarde el archivo. Tenga en cuenta que este tutorial no intenta           demostrar un diseño receptivo; estos estilos simplemente generan un resultado razonablemente interesante.
    
    ![](https://github.com/zazi479/Flask-Python/blob/0db5417f7bab437b05cfe36c761045f58b10ae4e/fotos%20flask/foto21.png)
    
Puede ejecutar la aplicación en este punto, pero debido a que no ha utilizado la plantilla base en ninguna parte y no ha cambiado ningún archivo de código, el resultado es el mismo que en el paso anterior. Complete las secciones restantes para ver el efecto final.
    
    
    
#   Crear un fragmento de código
    
 Debido a que las tres páginas que crea en la siguiente sección se extienden layout.html, se ahorra tiempo al crear un fragmento de código para inicializar un nuevo archivo de plantilla con la referencia adecuada a la plantilla base. Un fragmento de código proporciona una pieza coherente de código de una sola fuente, lo que evita errores que pueden aparecer cuando se usa copiar y pegar del código existente.

-   En VS Code, seleccione Archivo ( Code en macOS) > Preferencias > Configurar fragmentos de usuario .

-   En la lista que aparece, seleccione html . La opción puede aparecer como "html.json" en la sección Fragmentos existentes de la lista si ha creado fragmentos            anteriormente.

-   Después de que se abra VS Code html.json, agregue la siguiente entrada dentro de las llaves existentes (los comentarios explicativos, que no se muestran aquí,          describen detalles tales como cómo la $0línea indica dónde coloca el cursor VS Code después de insertar un fragmento):
    
```
   "Flask Tutorial: template extending layout.html": {
    "prefix": "flextlayout",
    "body": [
        "{% extends \"layout.html\" %}",
        "{% block title %}",
        "$0",
        "{% endblock %}",
        "{% block content %}",
        "{% endblock %}"
    ],

    "description": "Boilerplate template that extends layout.html"
},
  
```
    
    
Guarde el html.jsonarchivo ( Ctrl+S ).

Ahora, siempre que comience a escribir el prefijo del fragmento, como flext, VS Code proporciona el fragmento como una opción de autocompletar, como se muestra en la siguiente sección. También puede usar el comando Insertar fragmento para elegir un fragmento de un menú.

Para obtener más información sobre fragmentos de código en general, consulte Creación de fragmentos .

    
    
#   Use el fragmento de código para agregar páginas
    
Con el fragmento de código en su lugar, puede crear rápidamente plantillas para las páginas Inicio, Acerca de y Contacto.

1.  En la templates carpeta, cree un nuevo archivo llamado home.html, luego comience a escribir flextpara ver que el fragmento aparece como una finalización:
    
    Cuando selecciona la finalización, el código del fragmento aparece con el cursor en el punto de inserción del fragmento:
    
![](Cuando selecciona la finalización, el código del fragmento aparece con el cursor en el punto de inserción del fragmento:)
    
2.   En el punto de inserción en el bloque "título", escriba Homey en el bloque "contenido", escriba <p>Home page for the Visual Studio Code Flask tutorial.</p>y luego guarde el archivo. Estas líneas son las únicas partes únicas de la plantilla de página extendida:

![](https://github.com/zazi479/Flask-Python/blob/d9c7a67faf6a7c24961116a9f004cd4200400d0f/fotos%20flask/home.png)
    
3.  En la templates carpeta, cree about.html, use el fragmento para insertar el marcado repetitivo, inserte About usy <p>About page for the Visual Studio Code Flask tutorial.</p>en los bloques "título" y "contenido", respectivamente, luego guarde el archivo.
  
![](https://github.com/zazi479/Flask-Python/blob/d9c7a67faf6a7c24961116a9f004cd4200400d0f/fotos%20flask/about.png)

4.  Repita el paso anterior para crear templates/contact.html usando Contact usy <p>Contact page for the Visual Studio Code Flask tutorial.</p>en los dos bloques de contenido.
 
![](https://github.com/zazi479/Flask-Python/blob/d9c7a67faf6a7c24961116a9f004cd4200400d0f/fotos%20flask/contact.png)
    
5.  En app.py, agregue funciones para las rutas /about/ y /contact/ que hacen referencia a sus respectivas plantillas de página. También modifique la homefunción para usar la home.htmlplantilla.
    
 ![](https://github.com/zazi479/Flask-Python/blob/d9c7a67faf6a7c24961116a9f004cd4200400d0f/fotos%20flask/app.png)
    
    
    
#   Ejecute la aplicación
Con todas las plantillas de página en su lugar, guarde app.py, ejecute la aplicación y abra un navegador para ver los resultados. Navegue entre las páginas para verificar que las plantillas de página están ampliando correctamente la plantilla base.
    
 ![](https://github.com/zazi479/Flask-Python/blob/6596c845b0a125e4350543d141b3cb47ecab82d6/fotos%20flask/final.png)
    
    
 **Nota : si no ve los cambios más recientes, es posible que deba actualizar la página para evitar ver un archivo en caché.**
    
    He reiniciado el servidor Flask, el VisualStudio,el navegador y he probado en varios navegadores distintos y no me funciona da el siguiente error.
    
![](https://github.com/zazi479/Flask-Python/blob/6596c845b0a125e4350543d141b3cb47ecab82d6/fotos%20flask/error.png)
