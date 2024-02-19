# Vector DBs - Recuerdos de una IA

## Preparación del entorno

El sistema requiere de docker y python3, que se suponen ya instalados.

Para abrir los notebooks existen múltiples opciones, por ejemplo [VS Code](https://code.visualstudio.com/) con la extensión de [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python) y [Jupyter](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter).

> Si no se dispone de tarjeta gráfica NVIDIA será necesario cambiar "cuda" por "cpu" en los notebooks donde corresponda.

Los ejercicio requieren una cuenta en OpenAI para obtener una API Key. La [API Key](https://platform.openai.com/api-keys) se debe guardar en un fichero .env en la raíz del proyecto con el siguiente formato:

```shellscript
OPENAI_API_KEY=sk-cccx7u1...mWtdU3rso1vM
```

Levantamos Qdrant en local con docker

```shellscript
docker run -p 6333:6333 -p 6334:6334 -v $(pwd)/q_storage:/qdrant/storage:z qdrant/qdrant
```

Podemos acceder al Dashboard de Qdrant en http://localhost:6333/dashboard

Instalamos un entorno virtual de python y las dependencias necesarias

```shellscript	
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

## Guión del meetup

1. Presentación. Introducción a las bases de datos vectoriales
1. Ejemplo de uso de Qdrant con vectores básicos
1. Breve introducción a la lib sentence-transformers (Huggingface)
1. Carga de un dataset de películas de star wars (chunks)
1. Búsqueda semántica de películas con libs opensource
1. Introducción OpenAI API
1. Carga de dataset con OpenAI Embeddings API+LangChain
1. Búsqueda semántica de películas con LangChain+Qdrant+OpenAI 
1. Uso de LangChain para chat conversacional
1. Creamos contenido original, película Rey Legacy.
1. Verificamos que el chat no conoce información sobre la nueva película.
1. Cargamos la nueva película en Qdrant (my_movie).
1. Usamos el chat para preguntar por la nueva pelicula.
1. Ampliamos la información en Qdrant para preguntar en el chat.
1. Conclusiones y preguntas



