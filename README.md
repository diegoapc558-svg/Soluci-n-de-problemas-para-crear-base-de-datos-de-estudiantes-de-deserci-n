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

También es importante verificar que la biblioteca **Pandas** esté instalada para no obtener errores al compilar el código


