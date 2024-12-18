# Sistemas-RAG-con-bases-de-datos-vectoriales 📊

## :book: Descripción y contenido

Este repositorio contiene los componentes necesarios para contruir sistemas RAG segun unas instrucciones. El repositorio está compuesto por:

- `RAG_ingles.ipynb` - Documento que contruye un RAG con Ollama que da respuestas en inglés a partir de datos de una página web.
- `RAG_espanol.ipynb` - Documento que contruye un RAG con Ollama que da respuestas en castellano a partir de datos de un documento `.pdf`.
- `GUI_RAG_ingles.ipynb` - Versión del primer RAG usando una GUI para las consultas a Ollama.
- `RAG_mongoatlas.ipynb` - Versión del primer RAG que guarda los datos obtenidos de la web en una base de datos en Mongo Altas.
  
## :wrench: Requisitos previos

### :arrow_down: Clonar repositorio en local

Clona este repositorio en tu máquina local usando la URL o usando una clave SSH.

Con URL

~~~
git clone https://github.com/yoloman0001/Desenvolvemento-integracion-scripts-en-Python.git
~~~

Con SSH key

~~~
git clone git@github.com:yoloman0001/Desenvolvemento-integracion-scripts-en-Python.git
~~~

### :link: Instalar dependencias

Crea un environment con conda (opcional).

~~~
conda create --name nombre-environment python=3.12
~~~

Las dependencias necesarias vienen definidas en el archivo `requirements.txt`.
~~~
pip install -r requirements.txt
~~~

### :llama: Ejecutar Ollama en un Docker

Crea un network para Ollama

~~~
docker network create ollama_network
~~~

Lanza un contedor que apunte al puerto 11434 (de forma predeterminada, Ollama siempre apunta a este puerto).

~~~
docker run -v ollama:/root/.ollama -p 11434:11434 --name ollama --net=ollama_network ollama/ollama
~~~

## :bookmark_tabs: Instrucciones

**1. RAG en inglés que crea vector store a partir de datos de una página web.**

Ejecuta el archivo `RAG_ingles.ipynb`, puedes cambiar la URL por una de tu elección.

~~~
python RAG_ingles.ipynb
~~~

**2. RAG en castellano que crea vector store a partir de uno o varios ficheros pdf.**

Ejecuta el archivo `RAG_espanol.ipynb`, el cuaderno tomará el PDF que viene incluido en este repositorio, pero puedes cambiarlo por otro.

~~~
python RAG_espanol.ipynb
~~~

**3. Crear unha GUI para uno de los RAGs anteriores.**

Ejecuta el archivo `GUI_RAG_ingles.ipynb`, luego accede a la URL local de la interfaz Gradio desde navegador y realiza las consultas.

~~~
python GUI_RAG_ingles.ipynb
~~~

**4. RAG contra Mongo Atlas.**

Para conectarse a Mongo Atlas sigue los siguientes pasos: 

- Inicia sesión en MongoAtlas

- En la sección _Database Access_ dale a _Add New Database User_

- Crea un cluster y selecciona la opción _Add My Own Data_

- Crea una base de datos con nombre `rag` y una coleccion de nombre `info_about_spain`

- En la sección _Network Access_ añade tu dirección IP

- Elige como método de conexión _Connect your application_

- Elige de Driver `Python` y de versión `3.6 or later`

Tras seguir estos pasos, recibirás una cadena similar a esto:

`mongodb+srv://username:password@cluster0.xxxxx.mongodb.net`

Introdúcela en el cuaderno `RAG_mongoatlas.ipynb` en la siguiente sección:

~~~
client = MongoClient('mongodb+srv://username:password@cluster0.xxxxx.mongodb.net')
db_name = client['rag']
collection_name = db_name['info_about_spain']
ATLAS_VECTOR_SEARCH_INDEX_NAME = 'vector_index'
~~~

Para terminar, ejecuta el cuaderno paso a paso y comprueba que se guardaron los datos correctamente en Mongo Atlas.