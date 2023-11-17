<p align='center'>
<img src ="https://d31uz8lwfmyn8g.cloudfront.net/Assets/logo-henry-white-lg.png">
<p>

<h1 align='center'>
 <b>PROYECTO INDIVIDUAL Nº2</b>

 # <h1 align="center">**`Telecomunicaciones`**</h1>


# Acceso a Internet dentro de Argentina (2022-2014)

## **Introducción**

Este proyecto se realizó desde el rol de un Data Analyst cuya meta es la elaboración de un análisis de datos solicitado para el `INDEC`. Dicha institución realiza anualmente informes en el cual proporciona la cantidad de accesos a Internet según tipo de conexión, las distintas tecnologías de banda ancha ya sea a nivel nacional, provincial o localidad.

El objetivo del `INDEC` es proporcionar información y datos estadisticos sobre el acceso en general en Argentina. Hoy en día acceder a la internet se considera de primera necesidad que promueve el desarrollo personal, actividades diarias, tales como ocio, trabajo, gestiones administrativas, entre otros. Por otro lado, facilita el acceso a la información, comunicación  y entretenimiento. 

Para cumplir con ello, los datos iniciales que se utilizan son derviados de encuesta a proveedores del servicio de acceso a internet, durante los años 2014-2022, que es de público acceso en la página oficial de ENACOM. 
Podemos acceder a ellos desde [Datos oficiales](https://datosabiertos.enacom.gob.ar/dashboards/20000/acceso-a-internet/)

## **Contexto**

En el contexto actual del siglo XII, el avance de internet, no es una novedad. Sin embargo, dependiendo de los recursos de cada país, el acceso puede ser limitado o nulo. Con lo cual, el gobierno ha desarrollado políticas de financiamiento implementadas a través del Fondo Fiduciario del Servicio Universal (FFSU) para llevar conectividad a los sectores vulnerables y zonas geográficas aisladas o de difícil acceso, con el objetivo de reducir la brecha digital en todo el país.

El Estado nacional, por medio de ENACOM, considera a la conectividad un factor indispensable para el crecimiento económico y la igualdad de oportunidades para todas y todos. Por ello, impulsa, financia e implementa programas que requieren de la articulación del sector público y el sector privado en pos de favorecer la expansión de la infraestructura de Internet en la Argentina.

## **Desarrollo**

A partir de los datos obtenidos desde ENACOM, se procederá a realizar una revisión general de todas las tablas, para verificar la calidad de la información para luego asi proceder a realizar un dashbord en el cual contendrá indicadores/metricas para informar sobre el acceso de internet en Argentina.

Para ello, se realizará en una primera instancia la extracción, transformación y carga de datos(ETL), luego en una segunda instancia un analisis exploratorio de datos (EDA), y finalmente el dashboard en Power BI.

### Datos

A continuación se presentan las 15 tablas que se accedieron:

1. Penetración del servicio de Internet fijo (métrica: hogares) <br>
2. Penetración del servicio de Internet fijo (métrica: población)<br>
3. Número total de accesos al servicio de Internet fijo por banda ancha y banda angosta (trimestral)<br>
4. Número de accesos al servicio de Internet fijo por banda ancha y banda angosta en cada provincia (trimestral)<br>
5. Número de accesos al servicio de Internet fijo por tipo de tecnología. Total nacional (trimestral)
6. Número de accesos al servicio de Internet fijo por tipo de tecnología en cada provincia (trimestral)<br>
7. Velocidad Media de bajada de Internet fijo<br>
8. Velocidad media de bajada de Internet fijo por provincia<br>
9. Distribución de los accesos totales nacionales a Internet fijo por velocidad de bajada (último trimestre disponible)<br>
10. Acceso a Internet Fijo por rangos de velocidad de bajada y provincia<br>
11. Accesos a Internet fijo por velocidad bajada y provincia (sin rango)  <br>
12. Ingresos trimestrales de los operadores por el servicio de Internet fijo <br>
13. Número de accesos al servicio de Internet fijo por velocidad de bajada en cada localidad declarada <br>
14. Número de accesos al servicio de Internet fijo por tecnología en cada localidad declarada Categoría <br>
15. Listado de localidades con conectividad a internet, con detalle por tipo de conexión.


El mismo se puede acceder a la siguiente carpeta de [Dataset](https://github.com/nuggi46/PI_DA/tree/main/datasets)

### Análisis de los datos

A lo largo del proyecto, se investigó tabla por tabla, para analizar tendencias, la validez de cada una.
Se procedió a realizar gráficos, agrupaciones, analisis de veracidad en los datos, entre otros.

En el siguiente notebook se puede ver las distintas conclusiones [Analisis exploratorio](/EDA.ipynb)

- `Tabla 1:` La misma contiene información relacionada al acceso por cada 100 hogares por provincia.
Por ejemplo, cada 100 hogares en Buenos Aires, 78 hogares tienen acceso a internet.

A continuación se presenta la distribución de los accesos sin considerar año o provincia:

![Distribución acceso x hogar](/images/imagen_1.png)

En base a el gráfico se podría decir que el promedio de acceso cada 100 hogar se encuentra cada 30. Pero luego si segmentamos la información por año:

![Distribución acceso x hogar 2](/images/imagen_2.png)

Se puede visualizar que desde el 2014 hay un aumento sostenido del acceso de internet, y para el 2022 se encuentra en un rango de 60-70 hogares cada 100 en promedio.

Para más información se puede acceder al EDA.

- `Tabla 2:` La misma contiene datos de accesos por cada 100 hogares y cada 100 habitantes sin distinguir las provincias.
Esta tabla dice por ejmplo que por cada 100 habitantes para el cuarto trimestre del 2022, que solo 24 usuarios a internet. En cambio para el mismo periodo que por cada 100 hogares, 77 tienen acceso a internet. Esto resulta un poco contradictorio, ya que si un hogar tiene 5 integrantes, solo se está asumiendo que una persona tiene acceso a internet. Habría que investigar mas sobre como se calcula el indicador.

De todas maneras se analiza este indicador durante el periodo 2014 a 2022:

![Distribución acceso x habitantes 2](/images/imagen_3.png)


Nuevamente se puede visualizar un crecimiento sostenido, a excepción de una caida entre 2019/3 a 2020/01. La pandemia dio inicio en marzo del 2022. Lo que si se dio en ese periodo fue un cambio de gobierno, suba fuerte de tarifas y tipo de cambio, lo cual puede responder a esa caida de acceso.

- `Tabla 3:`  Esta tabla indica la cantidad de usuarios por periodo en el pais que acceden a internet, ya sea por banda ancha o dial up(El famoso ruidito que hacia el telefono al azar el tubo cuando se usaba internet,y si, aunque no parezca, esa tecnología se sigue usando en internet, según los datos oficial a 2022/4, aproximadamente 12.000 usuarios lo siguen teniendo)

A continuación se muestra la evolución del crecimiento porcentual del acceso de banda ancha (esto tambien se puede ver como la metrica/kpis de nuevos accesos):

![Evolucion porcentual banda ancha](/images/imagen_4.png)

Como se puede visualizar hay un crecimiento sostenido entre 0.01%-4% a lo largo de estos 8 años, a excepción del 2019/4


Por otro lado se puede ver la evolución de crecimiento del dial-up:

![Evolucion porcentual dial up](/images/imagen_5.png)

Como era de esperarse, el crecimiento es nulo, de hecho está en proceso de desuso.


- `Tabla 4:` Esta tabla tambien muestra el numero de usuarios por banda ancha/dial up pero desagregado por provincia.

A continuación se presenta solamente la evolución por banda ancha por provincia:

![Evolucion porcentual banda ancha x provincia](/images/imagen_6.png)

La mayor parte de las provincias comparten un crecimiento sostenido, a diferencia de provincias coomo San Luis, La Rioja y Santiago del Estero que en periodos puntuales tuvieron un golpe de crecimiento puntual.

- `Tabla 5:` Esta tabla contiene numero de accesos por tipo de tecnologia, ya sea ADL, modem, wireless, fibra óptica, entre otros. La misma, si bien fue analizada en el EDA, finalmente no fue considerada ya que, para el 2022/4 hay cerca de 11 millones de usuarios y en el mismo, solo muestra 11, por lo cual indica que los datos fueron truncados.

- `Tabla 6:` Esta tabla es complementaria a la tabla 5, con la diferencia que muestra por provincia los numeros de accesos por tipo de tecnologia. Y también se encuentra truncada, es dificil ya que hace la diferencia entre 11.900.000 o 11.100.000 de usuarios.

- `Tabla 7:` Esta tabla contiene la velocidad media de bajada por periodo. En un principio se consideró un error de datos porque a 2022/04 segun esta tabla, la velocidad media es de 10 megas, cuando uno esperaría una mayor cantidad de megas. Pero luego de una investigación, efectivamente los datos son correctos, segun Wikipedia: Una problemática del Internet en la Argentina es que el 4G del país es uno de los 10 más lentos del mundo. El promedio de velocidad de descarga en la Argentina es de 12,53 Mbps. Para mayor información, acceder al sgte [link](https://es.wikipedia.org/wiki/Internet_en_la_Argentina#:~:text=El%20promedio%20de%20velocidad%20de,(13%2C56%20Mbps)).

A continuación se puede ver la evolución promedio de la velocidad:

![Evolucion velocidad de conexión media](/images/imagen_8.png)

Como se puede visualizar entre a partir del 2018, hay un cambio en la velocidad media. Esto seguramente se debe a un cambio en la estimación de los datos, por lo cual se descarta la tabla.

- `Tabla 8:` Esta tabla es igual que la tabla 7, con la diferencia ed la desagregación por provincia. Hay un cambio en los datos a partir del 2018 en adelante. Se podria utilizar si solo se considera a partir del 2018 en adelante. Para mayor detalle acceder al EDA.

- `Tabla 9:` Esta tabla contiene los usuarios con acceso a internet por rango de velocidad.

A continuación se puede visualizar para un periodo puntual los crecimientos/decrecimientos por rangos de velocidad. La idea es ver si los usuarios migraron a otras velocidades:

![Migración velocidad](/images/imagen_9.png)

Se puede visualizar que hay una caida en casi todos los rangos y eso debe por un aumento de usarios en el rango mayor a 30 megas. Esto es esperable, dado que actualmente los costos de accesos son muchos más economicos, permitiendo migrar a una mayor velocidad. 

A continuación se puede ver la migración a través del tiempo, en el cual se ve la tendencia hacia mayores velocidades:

![Evolución Migración velocidad](/images/imagen_10.png)


- `Tabla 10:` Es una tabla complementaria a la tabla 9, se accede a la cantida de usuarios por rangos de velocidad y provincia.

A modo de ejemplo se adjunta un solo rango de velocidad para visualizar su evolución en el tiempo por provincia:

![Evolución Migración velocidad x provincia x 512](/images/imagen_11.png)

Queda claro que a medida que pasa el tiempo, en todas las provincias la selección de tener la velocidad más baja queda obsoleto. Para acceder a otros rangos, dirigirse al EDA.

- `Tabla 11:` Esta tabla contiene la cantidad de usuarios por velocidad de bajada puntual desagregado por provincia.

A continuación se puede visualizar en el siguiente gráfico en que velocidades hay más usuarios y en que años:

![Mapa de calor](/images/imagen_12.png)

Con este gráfico, se puede identificar rapidamente que por ejemplo que desde 2019 en adelante, la mayor concentración de usuarios se concentra en 50 Megas.

- `Tabla 12:`  Esta tabla contiene los ingresos de los operadores por el servicio de internet.

A continuación se muestra la evolución:

![Ingresos](/images/imagen_13.png)

Los ingresos a 2022/04 son de 70.000 pesos, lo cual no resulta confiable. Ya que si son 11 millones de usuarios, cobrando a 2.000 pesos el servicio, el ingreso seria de 22 millones un solo mes. Por otro lado, en Argentina debido a la inflación, los precios aumentan pero se necesita al mismo tiempo la cantida de usuarios, para verificar si el aumento de ingresos es debido a precio nominal o cantidad de usuarios.

- `Tabla 13:` Esta tabla no diferencia el periodo, solamente contiene por localidad/partido/ provincia la cantidad de usuarios en cada velocidad puntual.

Se pueden obtener las localidades con mas accesos de cada provincia y asi tambien donde menor hay acceso.
En este caso, Buenos Aires, que tiene más acceso entre todas las provincias, las localidades con mayores accesos son:San Martin, Florencio Varela y Almirante Brown.

- `Tabla 14:` Contiene los usuarios por los tipos de tecnologia desagregado por provincia/partido/localidad sin especificar el periodo

- `Tabla 15:` Esta es una tabla complementaria a la tabla 14, ya que solo informa si contiene o no el tipo de tecnologia por
provincia/partido/localidad sin especificar el periodo.


## **Conclusiones**

Tras analizar las 15 tablas, se descartan para la creación del dashboard la tabla 5,6,7,8 y 12. La tabla 14 se considera, aunque excluyendo CABA. A continuación se realizan los siguientes comentarios:

- A medida que transcurre los años el acceso a internet se ha ido incrementando sostenidamente. Esto se puede deber en parte por las politicas del gobierno y por la disminución de costos en general.

- Las provincias/ciudades con mayor acceso son Capital Federal, Buenos Aires, Tierra del Fuego, Córdoba. Esto también es de esperarse, ya que son ciudades con mayor desarrollo.

- Por otro lado, las provincias con menor acceso son: Chaco, Santa Cruz, Santiago del Estero y Formosa. Esto también es de esperarse ya que son las provincias con menores recursos del pais a excepción de Santa Cruz. En el caso de Santa Cruz, habría que verificar los datos o en todo caso, sería por una cuestión de innaccesibilidad a la zona.

- Con la reducción de costos de internet, a través del tiempo la población fue migrando a mayores velocidades, siendo así las más empleados 10,30,50 y 60 megas. Esto tambien se encuentra relacionado con el tipo de servicio que ofrecen los servicios de telecomunicaciones y los planes de banda de ancha.

- Para mayor información complementaria, se puede acceder a los informes de INDEC: [Informes](https://www.indec.gob.ar/indec/web/Nivel4-Tema-4-26-153/)







