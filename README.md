# **PROYECTO INFINITE PLAY** 🎬

## **URL al vídeo de la presentación:**

https://youtu.be/KxBmlQzjztw

## **Explorando el Séptimo Arte a través de Datos y Tecnología**
### **Participantes en el proyecto** 📝

_Sigue los links y hecha un vistaso a ell gran talento humano que hace parte de este proyecto_

🎞 [Paola Jineth Sánchez Solórzano](https://www.linkedin.com/in/paola-s%C3%A1nchez-sol%C3%B3rzano-5a05751b4/)

🎞 [Gloria González Muñoz](https://www.linkedin.com/in/gloria-gonzalez-105500107/)

🎞 [Silvia Marrero Pazos](https://www.linkedin.com/in/silvia-marrero-pazos-0b95b083/)

🎞 [Margarita María Torres Rodriguez](https://www.linkedin.com/in/margarita-torres-r/)

🎞 [Mábel Martínez Rodríguez](www.linkedin.com/in/mabelmr)

## **1. Resumen**
La plataforma de streaming BHO se encuentra en una búsqueda constante para mejorar la calidad de su contenido y la satisfacción de sus usuarios. Nuestro proyecto consiste en aplicar técnicas de análisis de datos para identificar cuáles son las películas y cortometrajes más populares y mejor valorados desde 2010 hasta la fecha. Esto ayudará a BHO a tomar decisiones informadas sobre qué contenido promocionar y destacar en su plataforma.

El objetivo es identificar las películas y cortos más populares en la plataforma BHO, basándonos en criterios como las calificaciones, el número de visualizaciones, y las reseñas de los usuarios. Analizar la evolución de las preferencias de los usuarios a lo largo de los años y determinar las tendencias en la industria cinematográfica. Proporcionar recomendaciones específicas para la promoción de contenido en las diferentes secciones de la plataforma.

## **Fases del Proyecto** 📊

### **Fase 1: Extracción de Datos de API de MoviesDataset** 🎥

En esta fase, usaremos la API de MoviesDataset, que contiene una gran cantidad de información sobre películas, incluyendo detalles como títulos, géneros, años de lanzamiento y más. Vuestra tarea será hacer solicitudes a esta API y extraer información relevante sobre las películas. En concreto, tendréis que sacar la siguiente información:

- Películas desde el 2010 hasta la actualidad.
- Películas que pertenezcan a los siguientes géneros: Drama, Comedy, Action.
- De cada una de las películas tendréis que sacar la siguiente información:
  - Tipo (si es corto o película).
  - Nombre de la película o el corto.
  - Año de estreno de la película o corto.
  - Mes de estreno de la película o corto.
  - Id de la película.

La documentación a la API la encontrarás aquí.

**NOTA:** La información de la API deberá ser almacenada en una lista de tuplas. Cada tupla corresponderá a una película, siguiendo el siguiente ejemplo:

```python
[("Pelicula", "Titanic", 1997, 12, "abc123"), ("Pelicula", "Los Goonies", 1985, 6, "abc456"), ...]
```

### **Fase 2: Extracción de Detalles de Películas con Selenium** 🌐

Una vez que tengan una lista de películas de la API, el siguiente paso es obtener información más detallada sobre ellas. Utilizarás la herramienta de automatización web Selenium para navegar a sitios web de reseñas de películas (IMDB y Rotten Tomatoes) y extraer detalles como calificaciones, actores y directores. En concreto, deberás extraer información sobre:

- Puntuación de IMDB (en caso de que la tenga).
- Puntuación de Rotten Tomatoes (Tomatometer).
- Dirección (director/a o directores/as de cada película).
- Guionistas (de cada película).
- Argumento.
- Duración (en minutos).
- Nombre de la película.

**NOTA:** La información de la API deberá ser almacenada en una lista de tuplas. Cada tupla corresponderá a una película, siguiendo el siguiente ejemplo:

```python
[(7.7, 77, "Richard Donner", ["Chris Columbus", "Steven Spielberg"], "Los Goonies son un grupo de amigos que viven en Goon Docks, Astoria, pero sus casas han sido compradas y van a ser demolidas. Sin embargo, vivirán su última aventura en busca de un tesoro que pueda salvar el barrio.", "Aventura", "1h 54min", "Los Goonies"), ...]
```

### **Fase 3: Extracción de Detalles de Actores con Selenium** 👥

El siguiente paso es extraer información detallada de los 10 principales actores de cada una de las películas extraídas en la Fase 1 utilizando Selenium (desde la página de IMDB). Deberéis tener en cuenta solo a los 10 primeros actores de cada película o corto (en caso de que los haya). La información que deberás extraer es:

- Nombre.
- Año de nacimiento.
- ¿Por qué es conocido?
- ¿Qué hace?
- Premios.

**NOTA:** La información de la API deberá ser almacenada en una lista de tuplas. Cada tupla corresponderá a una película, siguiendo el siguiente ejemplo:

```python
[("Adam Sandler", 1966, ["El aguador", "Little Nicky", "Un papá genial", "El chico ideal"], ["Reparto", "Producción", "Guion"], ["American Comedy Awards, USA", "Annie Awards"]), ...]
```

### **Fase 4: Extracción de Tablas de los Premios Oscar con Beautiful Soup** 🏆

En esta fase, trabajarán con la biblioteca Beautiful Soup para extraer información relevante de las tablas de los premios Oscar desde 2000. La tabla la encontrarás en el siguiente [enlace](https://www.example.com). La información que deberás sacar es:

- Fecha de la ceremonia.
- Mejor película.
- Mejor director.
- Mejor actor.
- Mejor actriz.

**NOTA:** La información de la API deberá ser almacenada en una lista de tuplas. Cada tupla corresponderá a una película, siguiendo el siguiente ejemplo:

```python
[(1990, 'Driving Miss Daisy', 'O. Stone', "D. Day-Lewis", 'J. Tandy'), ...]
```

### **Fase 5: Creación de una Base de Datos** 💾

Una vez que hayas reunido toda la información necesaria, es hora de pensar en la organización. Usando SQL, debes diseñar la estructura que debe tener la base de datos para almacenar toda la información recopilada y crear todas las tablas y conexiones entre ellas.

### **Fase 6: Inserción de Datos en la Base de Datos** 🛠️

Una vez que tengas la estructura de la base de datos lista, debes insertar todos los datos en la base de datos diseñada en el paso anterior.

### **Fase 7: Realización de Consultas para Obtener Información** 🔍

Con los datos almacenados en la base de datos, debes realizar consultas SQL para recuperar información específica. Las preguntas que deberás contestar son: podrán hacer consultas para encontrar películas con ciertas calificaciones, encontrar películas dirigidas por un director en particular o incluso obtener una lista de películas ganadoras de un premio Oscar en una categoría específica.

- ¿Qué géneros han recibido más premios Óscar?
- ¿Qué género es el mejor valorado en IMDB?
- ¿En qué año se estrenaron más películas?
- ¿En qué año se estrenaron más cortos?
- ¿Cuál es la mejor serie valorada en IMDB?
- ¿Cuál es la película mejor valorada en IMDB?
- ¿Qué actor/actriz ha recibido más premios?
- ¿Hay algún actor/actriz que haya recibido más de un premio Óscar?

## **2. Objetivos** 🎯

- Consolidar los conocimientos de Python y SQL.
- Utilizar control de versiones en equipo para aprender las ventajas y conflictos que genera.
- Implementar Scrum como marco de referencia para el desarrollo del producto, basándonos siempre en los valores de Agile como puntos clave del trabajo en equipo y la mejora continua.
- Mejorar la comunicación entre los miembros del equipo.
- Mejorar vuestras habilidades de comunicación en público al exponer el proyecto en la sesión final.
