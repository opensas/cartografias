Ejemplo con Mapa-cultura

1. Abrir archivo:
openrefine/data/geocode/cultura-0 (cleanse).csv

2. Facet por provincia

3. Edit cells - common transforms - trim leading and trailing whitespaces

4. Edit cells - common transforms - collapse consecutive whitespaces

5. Edit cells - common transforms - to title case

6. Cluster

7. Filter por " de", arreglar

Ciudad Autónoma De Buenos Aires
Santiago Del Estero
Tierra Del Fuego

--

8. Facet por departamento

9. Filtrar por los que comienzan por Departamento

10. Transformar celdas:

value.replace('Departamento de ', '')


11. Filtrar por los que comienzan por Cnel

12. Transformar celdas:
value.replace('Cnel.', 'Coronel ')

13. Edit cells - common transforms - collapse consecutive whitespaces


14. Filtrar por los que contienen '('

15. Transformar celdas:

value.split('(')[0].trim()

--

2. Geocodificar nuestra información utilizando servicios web
============================================================

Explicar: web service, rest, json

UI versus API - un ejemplo:

hands on: buscar Av. Corrientes 456, Ciudad Autónoma de Buenos Aires, Argentina

Open Street Map UI (para seres humanos)

UI: http://www.openstreetmap.org

UI: entrada: caja de texto
    salida:  mapa en pantalla

--

OpenStreetMap API (para aplicaciones)

http://open.mapquestapi.com/nominatim/v1/search.php?format=json&q=Av. Corrientes 456, Ciudad Autónoma de Buenos Aires, Argentina

(Av. Corrientes 456)[open.mapquestapi.com/nominatim/v1/search.php?format=json&q=Av. Corrientes 456, Ciudad de Buenos Aires, Argentina]

API: entrada: REST (url)
     salida:  json

avenida Corrientes 456, ciudad de buenos aires, argentina

(Av. Corrientes 456 con google maps)[http://maps.googleapis.com/maps/api/geocode/json?sensor=false&address=Av. Corrientes 456, Ciudad Autónoma de Buenos Aires, Argentina]

--


1. Facet - Custom text facet

row.index < 50

seleccionamos las primeras 100

(mostrar también la posibilidad de filtrar por star o flag)

2. Crear columna direccion geo a partir del campo direccion


value + ', ' +
cells.provincia.value + ', Argentina'

3. crear columna osm_geo

'http://open.mapquestapi.com/nominatim/v1/search.php?format=json&q=' + value.escape('url')

4. crear columna google_geo

'http://maps.googleapis.com/maps/api/geocode/json?sensor=false&address=' + value.escape('url')

5. eliminamos las que no trajeron resultado - columna osm_status

value.parseJson().lenght()
filter
remove rows
remove column status

5. add lat, lon column

columna lon:   value.parseJson()[0].lon.toNumber()
columna lat:   value.parseJson()[0].lat.toNumber()

remove column direccion_geo, osm_geo



open.mapquestapi.com/nominatim/v1/search.php?format=json&q=Av. Corrientes 456, Ciudad de Buenos Aires, Argentina

http://maps.googleapis.com/maps/api/geocode/json?sensor=false&address=Av. Corrientes 456, Ciudad Autónoma de Buenos Aires, Argentina
