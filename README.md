# Solucion-de-problemas-para-crear-base-de-datos-de-estudiantes-de-desercion
Se presenta la solución de posibles inconvenientes en el momento de crear un nuevo excel que contiene la información del estado de los estudiantes y aplicar el mismo al dashboard en power bi. Esto con el fin de actualizar los datos a la fecha de estudio. 
A continuación se presenta la explicación o desarrollo para la actualización de los datos estructurados en power bi, en este caso para el año 2026-3, en orden secuencial. Adicionalmente, se puntualizan posibles inconvenientes en este proceso. Para el mismo es recomendable el estudio previo del siguiente markdown:\
https://github.com/riudelectronicaUD/bases-datos-codigo.git
## Paso 1: Actualización de archivos excel **BD** y **estados**
La actualización de estas bases de datos se realizan a partir de la información actualizada en el Sistema de Gestión académica (SGA). Tener en cuenta que la información que se va a añadir a estos archivos también contiene la información del estado actualizado de los estudiantes de semestres pasados; sin embargo el código desarrollado en python (el cual se explica en el markdown citado anteriormente) limpia las filas repetidas, dejando los datos de una sola persona en una sola fila actualizada al periodo que corresponde.
## Paso 2: Generación de archivo en excel a partir de código en python
Una vez actualizados los datos en los dos archivos excel, ahora se unificarán en una sola base datos que genera el código en python; es importante verificar que los archivos que se encuentran en el script tengan el mismo nombre que los que están en la carpeta local.

```python
bd = pd.read_excel(r"D:\usuarios\Distrital\Downloads\BD_ (1).xlsx")
est = pd.read_excel(r"D:\usuarios\Distrital\Downloads\estados (1).xlsx")
```

También es importante verificar que la biblioteca **Pandas** esté instalada para no obtener errores al compilar el código.
## Paso 3: Verificación del archivo creado 
Al obtener el archivo actualizado denominado **BASE_COMPLETA**, es necesario verificar que los datos se han actualizado exitosamente; adicionalmente, hay que añadir una nueva columna que se observa en el excel que no está actualizada, esta es **Columna1**, luego verificar que las demás estén en el mismo orden para que en el momento de aplicar este nuevo archivo al dashboard en power bi, no haya ningun incoveniente con respecto a la información a la que se accede. Finalmente es necesario seleccionar toda la tabla en excel y darle formato de tabala, verificar que esta quede denominaa como **Tabla1**.
## Paso 4: Aplicación al dashboard en power bi
Al abrir el dashboard con respecto a deserción de estudiantes, se dirige a la herramienta **Transformar datos**. Se puede verificar que la tabla si tenga la misma ruta de acceso al excel generado a partir del código en python, en la sección **Origen** al costado derecho de la pantalla:

<a href="https://ibb.co/xKTnJ6f4"><img src="https://i.ibb.co/zWv3GZ7k/Captura-de-pantalla-2026-09-03-151720.png" alt="Captura-de-pantalla-2026-09-03-151720" border="0"></a><br /><a target='_blank' href='https://es.imgbb.com/'></a><br />

Posterior a esto, es posible que algunas columnas no tengan el mismo formato de datos que el que tenían anteriormente, por lo que hay que compararlo con el archivo que no ha sido actualizado para que las gráficas ilustrativas en el dashboard se presenten correctamente; asimismo, corregir si es necesario el contenido en cada columna, ya que por ejemplo los periodos pueden contener un guíon y otros no (**2026-3/20263**), para definir su contenido hay que seguir el mismo modelo del archivo anterior (sin actualizar) ya que esto también genera inconvenientes al trazar los ejes de tiempo en gráficas o la descripción a partir de tablas, del mismo modo que puede afectar las fórmulas o parámetros que dependen de dicha variable. Finalmente, se da click en **Cerrar y aplicar** para verificar que los datos han sido actualizados de forma exitosa.

