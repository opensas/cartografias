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

