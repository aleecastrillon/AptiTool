# Aptitool AddIn

Es una herramienta del tipo Add-In que se incorpora a ArcGIS para generar reporte del comportamiento de las variables según el componente que se seleccione. Esta herramienta es un complemento al proceso de zonificación que se desarrolla en la [UPRA](http://www.upra.gov.co/) y como tal hace falta que la estructura de almacenamiento se corresponda con la que se genera en este proceso, para mayor información dirigirse al repositorio de [zonificación](https://upraanalisis.github.io/zonificacion/).


## Instalación

El proceso de instalación es el siguiente:

1. Descargar el `Add-In`:

    Existen dos opciones de descarga, se puede descargar todo el repositorio o solo el ultimo Release del Add-In [Aquí](https://github.com/UpraAnalisis/AptiTool/releases/latest)

2. Luego hay dos opciones:

3. Si descargo el código, descomprimir y ejecutar el script `makeaddin.py`

4. Si descargo el release, descomprimir.

5. finalmente común a ambos copiar el archivo con extensión `.esriaddin` en el directorio:

    ```directorio Arcgis
    %USERPROFILE%\Documents\ArcGIS\AddIns\
    ```

Ingresar a la versión de ArcGis en la que se quiera instalar el Add-In y pegar el archivo.

## Uso de la herramienta

Para usar el Add-In Apptitool es necesario tener presente la estructura de Zonificación que se usa para las cadenas productivas, así como se ve en el siguiente gráfico:

<p align="center">
 <img src="Images\EstructuraNecesaria.png">
</p>

En la estructura se contempla que existe una GDB llamada **1_VARIABLES.gdb**, de esta el Add-In consultara la información contenida en el campo **Des***_ en el cual está contenido el metadato de la variable que se corresponde a El nombre de la Variable, la calificación y el valor que genero esta calificación.

### Modo de empleo

1. Cargar capas del criterio que se quieren consultar.

### Selección criterio

1. a.	Situé el criterio que se desea consultar en la tabla de contenido (TOC) de ArcMAP.

<p align="center">
 <img src="Images\SeleccionCriterio.png">
</p>

2. Asegurando que el criterio esta seleccionado en el TOC, proceder a hacer clic en el botón de la herramienta AptiTool

<p align="center">
 <img src="Images\SeleccionHerramienta.png">
</p>

3. Hacer clic en el punto de interés que se desea consultar.

<p align="center">
 <img src="Images\clickPunto.png">
</p>


### Selección Variables

Una vez realizado el proceso anterior el Add-In consulta en la gdb con las variables que corresponden a el criterio de interés, luego de eso carga los nombre en el menú desplegable y están listas para ser adicionadas a la visualización del mapa.

1. Seleccione variable a cargar en el en el menú desplegable

<p align="center">
 <img src="Images\SeleccionVariable.png">
</p>

2. Aparece un mensaje que advierte que la variable se está cargando, pulse OK

<p align="center">
 <img src="Images\CargarVariable.png">
</p>

3. La herramienta sitúa una vista más cercana al punto designado y carga la variable seleccionada al TOC.

<p align="center">
 <img src="Images\AcercarVista.png">
</p>

### Generación Reporte

1. Se carga la variable y mensaje Advierte si quiere generar reporte. (Reporte es Opcional)

<p align="center">
 <img src="Images\GenerarReporte.png">
</p>

2. Si decide generar reporte seleccione donde lo desea guardar.

<p align="center">
<img src="img\savrep.PNG">
</p>

3. De no generar reporte los datos quedan en un layer temporal llamado data y ahí los puede consultar.

<p align="center">
<img src="img\capcar.PNG">
</p>

4. El reporte aparece en Excel de la siguiente forma;  para el punto con coordenadas X,Y para la variable desempeño fiscal que para ese punto obtuvo una calificación de A2 por que presenta un valor de IC entre 0.4764 y 0.655, que será algo como lo siguiente:

 <p align="center">
 <img src="Images\Reporte.png">
</p>

5. Para realizar la consulta a múltiples variables a la vez solo es necesario ubicar estas en el TOC de ArcMap y luego seleccionar otra de la lista desplegable, esto produce un resultado que tiene las coordenadas del punto en cuestión, los nombres de las variables consultadas, sus aptitudes y los valores correspondientes.

<p align="center">
<img src="Images\ReporteMultiple.png">
</p>
