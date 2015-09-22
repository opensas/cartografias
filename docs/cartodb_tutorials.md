Ejercicio:

comunas
http://data.buenosaires.gob.ar/dataset/comunas

mostrar cartoCSS

- condiciones
zoom
comuna = 6

- labels
condiciones

- quantification

SELECT *,
round(area / 1000000) -6 as area2
FROM comunas_1
order by area2

filtros

mapa_cultura

demo:

filtrar por caba y teatros
y crear un dataset a partir de eso




metodos:

http://academy.cartodb.com/d/1.0_month.csv

- composite

- heatmap


- Ejercicio 1:

explorar los distintos tipos de gráficos
y pensar cuál sería más adecuado

filtrar los terremotos de magnitud mayor a 4

http://academy.cartodb.com/d/1.0_month.csv


- Ejercicio 2

Generar un chroropleth con esta información

Utilizar diversos métodos de quantificación

http://www.lavoz.com.ar/interactivo/el-mapa-del-cancer-en-cordoba-y-santa-fe

https://www.google.com/fusiontables/DataSource?docid=1ioORG-uXoB2iqetth6P9X0WxvnlWi7ghFjJkWjMV#rows:id=1

- Ejercicio 3

Reproducir el experimento de Snow
http://docs.cartodb.com/tutorials/conditional_styling.html
http://blog.rtwilson.com/updated-snow-gis-data/

opensas.github.io/cartografias/data/snow/cholera_deaths.zip
opensas.github.io/cartografias/data/snow/pumps.zip

Lesson 1:

cartoCSS

http://academy.cartodb.com/courses/05-academy-lite/lesson-1.html
http://academy.cartodb.com/courses/02-design-for-beginners/lesson-2.html

CartoCSS properties:
https://github.com/mapbox/carto/blob/master/docs/latest.md

labels
http://academy.cartodb.com/courses/02-design-for-beginners/lesson-4.html

quantification
http://academy.cartodb.com/courses/06-intermediate-design/lesson-1.html#quantification

SELECT *,
round(area / 1000000) -6 as area2
FROM comunas_1
order by area2

filtros
terremotos: http://academy.cartodb.com/d/1.0_month.csv



Ejercicio





agregar los labels para

cuando el zoom sea 6 mostrar los de magnitud >= 6

y a medida que aumentamos el zoom mostrar terremotos más debiles





labels
[zoom = xxx]

comunas

#comunas_1 [comuna = 6] {
  polygon-fill: #6B0FB2;
  polygon-opacity: 0.3;
  line-color: #055D00;
  line-width: 5;
  line-opacity: 1;
}

#comunas_1 [comuna = 6] [zoom > 12] {
  polygon-fill: #B40903;
  polygon-opacity: 0.8;
  line-color: #055D00;
  line-width: 15;
  line-opacity: 1;
}

-- mostrar los distintos tipos de gráficos



- ejercicio con el ejemplo de Snow
http://docs.cartodb.com/tutorials/conditional_styling.html

http://blog.rtwilson.com/updated-snow-gis-data/


opensas.github.io/cartografias/data/snow/cholera_deaths.zip
opensas.github.io/cartografias/data/snow/pumps.zip


----------------


resources:

http://academy.cartodb.com/

http://docs.cartodb.com/tutorials.html

http://docs.cartodb.com/tips-and-tricks.html

http://blog.cartodb.com

http://blog.cartodb.com/categories/how-to-guides/
http://blog.cartodb.com/categories/education/
http://blog.cartodb.com/categories/academy/

--

http://www.gdeltproject.org/about.html

http://blog.gdeltproject.org/


http://blog.gdeltproject.org/mapping-gdelt-in-cartodb-a-tutorial/
http://blog.gdeltproject.org/tutorial-instant-news-maps-using-cartodb-gkg-api/

datasets
http://blog.gdeltproject.org/gdelt-gkg-geojson-files-available/


cartodb tutorials
http://cartodb.github.io/training/

http://cartodb.github.io/training/advanced/cartodbjs-deep-dive.html

--
http://www.datavizcatalogue.com/



ejemplo muy completo

http://cartodb.github.io/training/advanced/nicar-15.html

buen ejemplo de carto js


--

carto academy

http://academy.cartodb.com/

--

projections

    4326 for WGS84, which defines the_geom;
    3857 for Web Mercator, which defines the_geom_webmercator.


sql cartodb - imprescindible!!!
http://academy.cartodb.com/courses/04-sql-postgis/lesson-1.html

the_geom vs the_geom_webmercator

SELECT cartodb_id, ST_Transform(ST_Centroid(the_geom), 3857) as the_geom_webmercator FROM comunas

SELECT cartodb_id, ST_Transform(ST_Buffer(the_geom,0.001), 3857) as the_geom_webmercator FROM comunas

el obelisco
SELECT
  ST_Transform(
    CDB_LatLng(-34.603720, -58.381606), 3857
  )
as the_geom_webmercator

SELECT
  1 as cartodb_id,
  ST_Transform(
    CDB_LatLng(-34.601779, -58.385421)
  , 3857)
  as the_geom_webmercator

dibujar un circulo de 50 metros alrededor del obelisco
SELECT
1 as cartodb_id,
  ST_Transform(
    ST_Buffer(
      CDB_LatLng(-34.603720, -58.381606)::geography,
      50
    )::geometry,
    3857
  )
as the_geom_webmercator


-- para ver la deformacion de las proyecciones
-- un circulo de 4500 kilometros
SELECT
1 as cartodb_id,
  ST_Transform(
    ST_Buffer(
      CDB_LatLng(-34.603720, -58.381606)::geography,
      4500000
    )::geometry,
    3857
  )
as the_geom_webmercator




calcular el área
SELECT
  cartodb_id,
  the_geom_webmercator,
  ST_Area(the_geom::geography) as area
from comunas

cacular la distancia al obelisco en metros

traer los que están a menos de 100 metros
SELECT
  cartodb_id,
  the_geom_webmercator,
  ST_Distance(
    the_geom::geography,
    CDB_LatLng(-34.603720, -58.381606)::geography
  ) as distancia
FROM
  cajeros
where
  ST_Distance(
    the_geom::geography,
    CDB_LatLng(-34.603720, -58.381606)::geography
  ) < 1000

http://gis.stackexchange.com/questions/155584/cartodb-postgis-near-function-distance-points-to-polygons

los 50 cajeros más cercanos al obelisco

SELECT
  cartodb_id,
  the_geom_webmercator,
  ST_Distance(
    the_geom::geography,
    CDB_LatLng(-34.603720, -58.381606)::geography
  ) as distancia
FROM
  cajeros
order by distancia asc
limit 50

http://blog.cartodb.com/nearest-neighbor-joins/

los puntos en una caja

SELECT
  *
FROM
  cajeros
WHERE
  the_geom &&
  ST_MakeBox2D(
    CDB_LatLng(-34.601779, -58.385421),
    CDB_LatLng(-34.608477, -58.372493)
  )

--

SELECT
  ST_X(ST_Centroid(the_geom)) as longitude,
  ST_Y(ST_Centroid(the_geom)) as latitude,
  banco,
  ST_Distance(
    the_geom::geography,
    CDB_LatLng(-34.603720, -58.381606)::geography) AS distance
  FROM cajeros
  ORDER BY distance ASC LIMIT 10

--

http://docs.cartodb.com/tips-and-tricks.html

--

Temas para clase cartodb avanzado

- cartocss
http://academy.cartodb.com/courses/05-academy-lite/lesson-1.html
http://academy.cartodb.com/courses/02-design-for-beginners/lesson-2.html
https://github.com/mapbox/carto/blob/master/docs/latest.md


marker-width
http://academy.cartodb.com/courses/02-design-for-beginners/lesson-3.html

quantification methods
http://academy.cartodb.com/courses/06-intermediate-design/lesson-1.html

labels
http://academy.cartodb.com/courses/02-design-for-beginners/lesson-4.html

torque
http://academy.cartodb.com/courses/01-beginners-course/lesson-4.html

multilayer

tipos de mapas
http://academy.cartodb.com/courses/06-intermediate-design/lesson-1.html



gis stack exchange
http://gis.stackexchange.com/
http://gis.stackexchange.com/questions/tagged/cartodb

projections

http://docs.cartodb.com/tutorials/projections.html

