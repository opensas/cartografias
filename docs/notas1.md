descarga mapas:

http://data.buenosaires.gob.ar/dataset/barrios

resources:
http://espacio.fundaciontelefonica.com.ar/2015/06/30/taller-cartografia-de-datos/

https://docs.google.com/document/d/1pGKYcQ88bIw6GRYDpx-67JTB3ffBaWyDszRtHhtmo-8/edit#heading=h.jwo083z6ge0b

--
Programa

*************************************

– Unidad I:
***********

Cartografía de Datos: orientado a información pública

Productos de interés público, periodismo de datos, aplicaciones cívicas, visualizaciones, aplicaciones móviles, APIs

Comprender los conceptos básicos y las herramientas disponibles. Usar alguna de ellas para dar los primeros pasos. Comprender las cosas que se pueden hacer y reconocer los recuros (humanos y materiales) necesarios para llevarlos a cabo.

--

Introducción al Open Data.

- Gobierno Abierto (transparencia, colaboración, participación, innovación - administracion obama)

Doctrina política que sostiene que los temas de gobierno y administración pública deben ser abiertos a todos los niveles posibles.

Se basa en tres ejes:

  Transparencia
  Colaboración
  Participación

Datos Abiertos
==============

Es una parte de una estrategia de Gobierno Abierto.

Definición: el conocimiento es abierto si cualquiera es libre de:

  acceder a él
  usarlo
  modificarlo
  y compartirlo
  sujeto, a lo sumo, a las medidas que preserven su autoría y apertura.

Esta definición está basada en el concepto de software libre.

Portales de datos

Son plataformas digitales que sirven para almacenar, compartir, conectar y visualizar bases de datos. El estándar de facto: CKAN

Qué es un dataset;

  Los conjuntos de datos agrupan uno o más recursos de datos así como la documentación que les da contexto.
- información estructurada (tabular, jerárquica)
- formatos (csv, excel, ods, json, xml)

Metadata:
 Información acerca del dataset:
  Título, Tags, Organización, Autor, Responsable, Email del Responsable, Frecuencia de actualización

API: application programming interface

GIS - Sistemas de información geográfica

- orígenes (https://en.wikipedia.org/wiki/John_Snow_%28physician%29)

https://upload.wikimedia.org/wikipedia/commons/thumb/2/27/Snow-cholera-map-1.jpg/643px-Snow-cholera-map-1.jpg

cómo se representan los datos y metadatos cartográficos;

http://gis.stackexchange.com/questions/664/whats-the-difference-between-a-projection-and-a-datum
http://help.arcgis.com/es/arcgisdesktop/10.0/help/index.html#//003r00000002000000

- Sistema de Coordenadas Geográficas
- Sistemas de Coordenadas Proyectadas - http://gis.stackexchange.com/a/1328/19461

tipos de formatos de datos
csv con coordenadas, csv con poligonos, geojson, shapes files, etc

De los metadatos a la información; qué datos pueden representarse en un mapa interactivo; ejemplos de visualización de datos cartográficos;

Ejemplos:

Visualizaciones

open data
http://www.asap.org.ar/observatorio/#/poder/PODEJEC?t=info


http://archivodecasos.com.ar/archivo/mapa/


- La dimensión temporal en los mapas.-

http://www.theguardian.com/society/ng-interactive/2015/sep/02/unaffordable-country-where-can-you-afford-to-buy-a-house

HotelViz: http://www.nardoz.com/HotelViz/

Creación de oficinas de Correo en EEUU
https://viz2.cartodb.com/viz/70bc854e-68fc-11e3-8e22-0e49973114de/public_map

Flota inglesa en la Primera Guerra Mundial
http://www.theguardian.com/news/datablog/interactive/2012/oct/01/first-world-war-royal-navy-ships-mapped

Muertes por tornados en EEUU en el último medio siglo
http://www.nytimes.com/interactive/2011/04/28/us/tornado-deaths.html?_r=0

El proyecto refugiados
http://www.therefugeeproject.org


Ediciones de OpenStreetMap de 2008
http://flowingdata.com/2009/01/08/animated-map-shows-one-year-of-edits-to-openstreetmap/



Indicadores educativos
http://blog.jazzido.com/indicadoresEducativosAR/#abandono/egb_1/2003

Cantidad de farmacias por habitantes en condiciones de jubilarse
http://pami.cartodb.com/viz/79ce56fc-6d0c-11e4-b9e4-0e018d66dc29/public_map

Votos en la ONU por la creación de un marco legal para la reestructuración de deuda
http://opensas.cartodb.com/viz/7eac5748-38ad-11e4-bce0-0e10bcd91c2b/public_map



Cartograma
http://th-mayer.de/cartogram/#population


Parte práctica

Un ejercicio simple con CartoDB

Sacar una cuenta
Subir un dataset que preparemos con provincia, depto y varios datos mas sacados del dataset del censo, y que hagan varios mapas

*************************

– Unidad II:
************

Presentación y uso práctico de tecnologías disponibles:

Normalización de datos con OpenRefine
- funciones básicas
- ejercicios

Geocodificación con OpenRefine
- concepto de api
- api versus UI (google maps, OpenStreetMap)
- json
- geocodificar con OpenRefine usando google maps API y OpenStreetMap API

El proyecto OpenStreetMap y la construcción colaborativa y abierta de la cartografía.
- cómo geolocalizar con CartoDb, OpenStreetMap, google maps -- NO FusionTables.

Ejercicio:
- tomar tus contactos de google
- bajarlos como csv
- geocodificarlos con OpenRefine
- subirlos a cartoDB y visualizarlos

<no>
Análisis de casos con los servicios de CartoDb y FusionTables; el proyecto Mapa Educativo del Ministerio de Educación y la Infraestructura de Datos Espaciales de Argentina (IDERA). El poder cartográfico de Google.
</no>

*************************************

– Unidad III: La frontera de los datos cartográficos.
*************

Qué es CartoDB?
- interfase web
- PostgreSQl + postgis  - base de datos relacional, SQL
- software libre
- servicio web

Usos avanzados de CartoDB
- nociones básicas de SQL
- consultas combinando tablas
- definiendo areas Custom (geojson.io)

El uso de APIs. (lo vimos en la anterior para hacer geocodificacion)

- explicar el ejempo de mapa cultural
- CartoDB como backend

??? Fuentes de datos primarias; el Sistema Nacional de Datos Públicos (SINDAP) y otras fuentes de datos.

??? Uso de BAHRA (cartografía oficial de argentina)
y los servicios de geocodificación (OSM, Google, etc);

los formatos de datos geoespaciales.

Los usos posibles de la información cartográfica;
-ejemplos de visualizaciones y aplicaciones

??? la proyección del BigData y la Internet de las cosas en la dimensión geoespacial. ???
--

**************************

- Unidad IV (el último encuentro)
************

Ejercicio de integración

Respuesta de consultas

Discutir los proyectos e ideas que pueda tener cada uno

*******************************

Algunos Links

GIS - sistema de información geográfica
https://es.wikipedia.org/wiki/Sistema_de_informaci%C3%B3n_geogr%C3%A1fica

origenes:
https://en.wikipedia.org/wiki/Geographic_information_system
https://en.wikipedia.org/wiki/John_Snow_%28physician%29
https://upload.wikimedia.org/wikipedia/commons/2/27/Snow-cholera-map-1.jpg

formatos más comunes

csv con coordenadas
https://en.wikipedia.org/wiki/Shapefile
http://docs.cartodb.com/tutorials/import_shapefile_in_cartodb.html
https://en.wikipedia.org/wiki/Geography_Markup_Language
https://en.wikipedia.org/wiki/GeoJSON

--
experiencias:

----
SQL

MUY BUENA intro a SQL en CartoDB
https://speakerdeck.com/andrewxhill/maps-lies-and-storytelling-p06-and-p07-sql-and-cartocss

Ejercicios

- open refine introductorio y avanzado
taller intro a open refine
https://github.com/opensas/taller_refine

- open refine

Slides a tomar de ejemplo
https://github.com/opensas/tutoriales
https://github.com/Nardoz/presentacion-hackaton/tree/gh-pages
http://www.nardoz.com/presentacion-hackaton/#/

Taller aprende el lenguaje de tu programador
http://www.nardoz.com/mapa-cultura/slides/mediaparty_rendered.svg
http://www.nardoz.com/mapa-cultura/slides/mediaparty_rendered.svg#3

herramienta online para editar y exportar geojson
http://geojson.io

cartodb-demo
http://opensas.github.io/cartodb-demo/#/
https://github.com/opensas/cartodb-demo

gobierno abierto y la apertura de datos
https://github.com/opensas/opendata
http://opensas.github.io/opendata/#/

apps

Aplicación Pami Presente
http://opensas.github.io/mapa-pami/main.html

Cantidad de farmacias por habitantes en condiciones de jubilarse
http://pami.cartodb.com/viz/79ce56fc-6d0c-11e4-b9e4-0e018d66dc29/public_map

Votos en la ONU por la creación de un marco legal para la reestructuración de deuda
http://opensas.cartodb.com/viz/7eac5748-38ad-11e4-bce0-0e10bcd91c2b/public_map


Visualizaciones

Cantidad de farmacias por provincia http://cdb.io/1x6E6MB

Cantidad de farmacias por provincia según la probación en condiciones de jubilarse http://cdb.io/1x6FbnC

Centros de jubilados por fecha de creación http://cdb.io/1sRwyIi

UGLs y Oficinas del PAMI http://cdb.io/1pyMmBA

Densidad de oficinas del PAMI http://cdb.io/1pyMKjB

Oficinas del PAMI agrupadas http://cdb.io/1pyN1CY

Oficinas del PAMI por fecha de creación http://cdb.io/YhFZIT

El web service está disponible aquí: http://opensas.cartodb.com/api/v2/sql?q=select * from geo_servicios_pami limit 10

-- ejercicio

Cargar los datasets de barrios, cajeros automaticos, comunas

SELECT
  *,
(
  select count(*) from cajeros as c
  where st_within(c.the_geom, b.the_geom)
) as cajeros
FROM
  barrios as b

http://data.buenosaires.gob.ar/dataset/cajeros-automaticos

http://data.buenosaires.gob.ar/dataset/barrios
http://data.buenosaires.gob.ar/dataset/comunas

ejercicio 2: censo 2010 por comunas


--

-- censo la nacion 2001-2010
http://interactivos.lanacion.com.ar/censo/#Poblacion_Total-intercensal

-- radios censales
http://www.indec.gov.ar/codgeo.asp

-- varios mapas con cartodb: http://indicesalta.esy.es/about/

http://blog.jazzido.com/2014/05/09/scrapeando-mapas-reconstruyendo-fracciones-y-radios-censales/

