
![GitHub repo size](https://img.shields.io/github/repo-size/scottydocs/README-template.md)
![GitHub contributors](https://img.shields.io/github/contributors/scottydocs/README-template.md)
![GitHub stars](https://img.shields.io/github/stars/scottydocs/README-template.md?style=social)
![visitor badge](https://PI02_SiniestrosViales_CABA.laobi.icu/badge?page_id=jwenjian.PI02_SiniestrosViales_CABA-query&query_only=true)

<p align=center>
<img src="src\logo.png" height = 150 weight=250>
<p>

# <h1 align="center">**`Siniestros Viales en la Ciudad Atónoma de Buenos Aires (CABA)`**</h1>

Bienvenidos a continuación se presenta el desarrollo del Proyecto Individual de Análisis de Datos

## Introducción


El presente proyecto se desarrolló bajo el perfil de un Data Analyst y tiene como finalidad la elaboración de un proyecto de análisis de datos para obtener información y conocimiento, este requerimiento es solicitado por el Observatorio de Movilidad y Seguridad Vial (OMSV), que es un centro de estudios que se encuentra bajo la órbita de la Secretaría de Transporte del Gobierno de la Ciudad Autónoma de Buenos Aires (CABA). La realización del proyecto permitirá a las autoridades locales tomar decisiones claves para mitigar la cantidad de víctimas mortales en los siniestros viales en la Ciudad Atónoma de Buenos Aires (CABA).


Mediante el análisis de los datos sobre los siniestros viales, también conocidos como accidentes de tráfico o accidentes de tránsito, entre los años 2016 y 2021, descubrí varias observaciones que pueden guiar a la toma de decisiones futuras por las autoridades. En este proyecto, compartiré mis hallazgos y brindaré recomendaciones que estan basadas en información que han sido derivados de un dataset de homicidios en siniestros viales en la Ciudad Autónoma de Buenos Aires (CABA).


## Contexto
Las muertes por siniestros viales en Argentina poseen cifras alarmantes los informes del Sistema Nacional de Información Criminal (SNIC), revelan que entre 2018 y 2022 se registraron 19'630 muertes en siniestros viales en todo el país.  Estas cifras equivalen a 11 personas por día que resultaron víctimas fatales por accidentes de tránsito.

Esta es una gran problemática que afecta a todas las provincias, si bien algunas se ven más afectadas que otras, sigue siendo un factor que da que hablar en cada territorio. Al 2022 los siniestros totales que suceden en la provincia de Buenos Aires representan el 30%. Los siniestros viales involucran a diversos tipos de vehículos y actores en las vías públicas, y estos son automóviles, motos, bicicletas, peatones, atropellos, vehículos de carga y pasajeros. 

Solo en 2022, el número de muertes por accidentes de tránsito alcanzó a 3'828 muertes fatales. Los expertos en la materia indican que en Argentina es dos o tres veces más alta la probabilidad de que una persona muera en un siniestro vial que en un hecho de inseguridad delictiva.


## 📊 Alcance del Proyecto

El siguiente proyecto contiene los siguientes desarrollos:

- Extracción Transformación y Carga sobre la data Hechos y de Victima
- Análisis Exploratorio de Datos
- Creación de Dashboard y Análisis con PowerBI
- Creación de KPIs

## Datos

Este proyecto se desarrolló en base al dataset denominado Homicidios, que se encuentra en formato de Excel y contiene dos hojas de datos :

- Hechos: contiene datos específicamente relacionados a los siniestros como lo son la fecha y hora del siniestro,  cantidad de víctimas, el lugar de hecho, la comuna, la dirección, la geolocalización, el tipo de víctima y los acusados.

- Víctimas: contiene datos relacionados con las víctimas y estos son la edad, el sexo, el rol, la fecha de fallecimiento, así como también la fecha del siniestro.

Los datos utilizados para este proyecto de análisis, estan en el siguiente [enlace de descarga](https://data.buenosaires.gob.ar/dataset/victimas-siniestros-viales) 


## **DESARROLLO DEL PROYECTO INDIVIDUAL ** :white_circle:

## **1. Etapa del proceso ETL** :

- Carga del archivo con extensión .xlsx con la libreria pandas.
- Luego se realizó el trabajo ETL(Extracción, Transformación y Carga) de las hojas de Hechos y de Víctimas.
- Se realizaron diversas transformaciones cumpliéndose con la estandarización de los datos se analizaron nulos y duplicados, se eliminaron columnas redundantes, entre otras tareas.
- Luego de las transformaciones y normalización de los datos se exportaron 2 archivos .csv de Hechos y Víctimas para realizar la respectiva carga las tablas en la Base de Datos de MySQl.


## **2. Análisis Exploratorio de los Datos (EDA)**

Una vez que los datos están limpios, es tiempo de revisar las relaciones que existen entre las variables de los datasets, encontrar si hay presencia de outliers o anomalías (que no tienen que ser errores necesariamente), y se verificó si hay algún patrón o conocimiento que sirva en un análisis posterior. Una gráfica muy representativa de este proceso es las nubes de palabras que nos mostrarán cuales son las palabras que se presentan con una mayor frecuencia, a continuación mostraremos la gráfica sobre la columna 'Dirección Normalizada' con lo cual se puede ver que las palabras 'gneral paz' y 'av' que representa a avenida son las que aparecen con mayor frecuencia en los sinistros viales 


<p align="center">
<img src="src\nube.png"  height = 300 weight=400>
</p>


## **3. Análisis de Datos **
- La principal causa de víctimas en las carreteras son las motos, seguidos de los peatones y los autos. Las motos causaron casí la mitad de la muertes representando el 42%. Esto pone de relieve el importante impacto y participación de las motos  en los accidentes de tráfico. Es crucial abordar factores como el comportamiento del conductor, la infraestructura vial y las medidas de seguridad de las motos para mitigar los riesgos asociados con los accidentes.

<p align="left" >
<img src="src\analisis01.png"  height = 400 weight=500>
</p>

- La mayor parte de accidentes ocurrieron en las comunas 1 , 4 y 9, es necesario indicar que estas comunas requieren una mayor atención para mejorar las medidas de seguridad vial. Factores como una mayor densidad de población, un mayor volumen de tráfico, redes de carreteras complejas y diversos modos de transporte que interactúan en estas comunas pueden estar contribuyendo a la mayor tasa de víctimas.

<p align="center">
<img src="src\analisis02.png" >
</p>

- El rango de edades involucrado en la mayor cantidad de accidentes es el que está comprendido entre los 18 a 35 años de edad. Aquí se debe de tener en cuenta factores como el aumento del volumen de tráfico, las velocidades más altas, las distracciones durante el la ruta pueden contribuir a una mayor incidencia de accidentes.

<p align="center">
<img src="src\analisis03.png" >
</p>

- El mapa donde se localizan los puntos donde ocurrieron los accidentes nos sirve de mucha ayuda ya que nos muestran las principales zonas donde existe una mayor frecuencia de accidentes, esto es el caso de que si filtramos por una específica comuna podemos reconocer las avenidas que presentan mayor cantidad de accidentes, esto nos sirve para realizar políticas urbanas y así mitigar la tasa de mortalidad por siniestros viales.


<p align="center">
<img src="src\analisis04.png" >
</p>

- Podemos reconcer que los días que presentan mayor cantidad de siniestros viales son los Lunes y Sábados, así como tambien los mese donde existen mayores frecuencias de accidentes son los meses de Noviembre y Diciembre.

- Se halló que el sexo Masculino es el que tiene un mayor porcentaje de siniestros viales con un 76%

<p align="center">
<img src="src\analisis05.png" >
</p>


## **4. Creación de KPIs**
* *Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior*

    Se define como **Tasa de homicidios en siniestros viales** al número de víctimas fatales en accidentes de tránsito por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico, en este caso se toman 6 meses. Su fórmula es:

    $\text{Tasa de homicidios en siniestros viales} = \frac{\text{Número de homicidios en siniestros viales}}{\text{Población total}}X100,000$


    En este caso, la *Tasa de homicidios en siniestros viales* del Semestre 2020 respecto al Semestre anterior del 2019 representa una mejor variación y esta por encima
    del objetivo del 10% y se cumple con el objetivo propuesto con un 34%.


* *Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior*

    Su fórmula es:

    $\text{Cantidad de accidentes mortales de motociclistas} = -\frac{\text{Víctimas moto año anterior - Víctimas moto año actual}}{\text{Víctimas moto año anterior}}X100$

    Donde:
    - $\text{Víctimas moto año anterior}$: Número de accidentes mortales con víctimas en moto en el año anterior
    - $\text{Víctimas moto año actual}$: Número de accidentes mortales con víctimas en moto en el año actual 

    En este caso, el año 2020 respecto anterior del 2019 sobre el número de accidentes mortales en moto representa una mejor variación y esta por encima
    del objetivo del 7% y se cumple con el objetivo propuesto con un 42%.

    
* *Reducir en un 19% la cantidad de accidentes mortales en el último año, en CABA, respecto al año anterior*

    Su fórmula es:

    $\text{Cantidad de accidentes mortales} = -\frac{\text{Víctimas año anterior - Víctimas año actual}}{\text{Víctimas año anterior}}X100$

    Donde:
    - $\text{Víctimas moto año anterior}$: Número de accidentes mortales con víctimas en el año anterior
    - $\text{Víctimas moto año actual}$: Número de accidentes mortales con víctimas en el año actual 

    En este caso, el año 2019 respecto anterior del 2018 sobre el número de accidentes mortales representa una mejor variación y esta por encima
    del objetivo del 19% y se cumple con el objetivo propuesto con un 30%.

## **5  Conclusiones**

Mis principales conclusiones sobre la evolución de los accidentes de tráfico en CABA son los siguientes:
 
✅ Del 2016 al 2018 existe una mayor cantidad de siniestros viales en los años posteriores esta se fue reduciendo (2019-2021) y se verificó que son las motos las que tienen mayor participación en accidentes así como los rangos de edades entre 18-35 años.  
  
✅ La comuna 1, es la que tiene la mayor concentración de accidentes y se verico que las avenidas "9 de Julio" y "Paseo Colón" son las que tienen asociadas un número mayor de víctimas.

✅ El rol de la víctima asociado a una mayor cantidad de accidentes es el Conductor en comparación con el pasajero acompañante.
 
✅ El accidente típico se produce un Sábado a las 7 horas en el mes de Diciembre. 


En función de lo anterior, se hacen las siguientes recomendaciones:


- Se deben de generar campañas de concientización en las comunas que tienen un alto número de víctimas; así como eliminar la contaminación visual en las principales avenidas ya que esto aumenta la distracción de los conductores.
- Realizar campañas respecto a la seguridad vial hacia el sexo masculino sobre el rango de edad de 18 a 35 años.
- Debede existir un reglamento más riguroso para la obtención de la licencia de vehículos y especificamente sobre quienes usan moto se debe establecer un control respecto al uso de casco certificado.
- En el mes de Diciembre se debe ser de reforzar la seguridad vial por medio de operativos policiales de control en las principales avenidas.


## 🛠 Tecnologías Utilizadas

![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)
![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)
![Power Bi](https://img.shields.io/badge/power_bi-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![MySQL](https://img.shields.io/badge/mysql-%2300f.svg?style=for-the-badge&logo=mysql&logoColor=white)
