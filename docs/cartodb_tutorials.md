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
order by Distancia asc
limit 50


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
