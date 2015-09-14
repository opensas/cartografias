# Solución del ejercicio sobre json:

1- Abrir un explorador (Firefox o Chrome)

2- Apretar F12 y seleccionar la consola JavaScript

3- Pegar el siguiente texto

```
var resultados = {
  "Heading" : "Buenos Aires",
  "RelatedTopics" : [
     {
        "Icon" : {
           "URL" : "https://duckduckgo.com/i/c8804af5.png",
        },
        "FirstURL" : "https://duckduckgo.com/Buenos_Aires",
        "Text" : "Buenos Aires The capital and largest city of Argentina..."
     },
     {
        "Icon" : {
           "URL" : "https://duckduckgo.com/i/2826ecf7.png",
        },
        "FirstURL" : "https://duckduckgo.com/Buenos_Aires_Province",
        "Text" : "Province of Buenos AiresThe largest and most populous Argentinian province."
     },
     {
        "Icon" : {
           "URL" : "https://duckduckgo.com/i/35bb000c.jpg",
        },
        "FirstURL" : "https://duckduckgo.com/Greater_Buenos_Aires",
        "Text" : "Greater Buenos Aires, the urban agglomeration comprising..."
     }
  ]
};
```

Acabamos de declarar una variable llamada 'resultados' con el objeto json devuelto por la consulta de DuckDuckGo.

Para cada una de las consultas requeridas, ingresar los siguientes comandos en la consola

4- Consultar el Heading

```
resultados.Heading
<- "Buenos Aires"
```

5- Consultar el url del ícono del primer resultado

```
resultados.RelatedTopics[0].Icon.URL
<- "https://duckduckgo.com/i/c8804af5.png"
```

6- Consultar el url del ícono del último resultado

```
resultados.RelatedTopics[2].Icon.URL
<- "https://duckduckgo.com/i/35bb000c.jpg"
```

7- Consultar el la cantidad de resultados retornados por la consulta

```
resultados.RelatedTopics.length
<- 3
```

