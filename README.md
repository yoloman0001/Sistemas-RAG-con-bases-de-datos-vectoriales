# Sistemas-RAG-con-bases-de-datos-vectoriales 📊

## :book: Descripción y contenido

Este repositorio contiene los componentes necesarios para contruir sistemas RAG segun unas instrucciones. El repositorio está compuesto por:

- `RAG_ingles.ipynb` - Documento que contruye un RAG que da respuestas en inglés a partir de datos de una página web.
- `RAG_espanol.ipynb` - Documento que contruye un RAG que da respuestas en castellano a partir de datos de un documento `.pdf`.
- 
  
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

## :bookmark_tabs: Instrucciones

1. RAG en inglés que crea vector store a partir de datos de una página web.

Ejecuta el archivo `RAG_ingles.ipynb`, puedes cambiar la URL por una de tu elección.

~~~
python RAG_ingles.ipynb
~~~

2. RAG en castellano que crea vector store a partir de uno o varios ficheros pdf.

Ejecuta el archivo `RAG_espanol.ipynb`, el script tomará el PDF que viene incluido en este repositorio, pero puedes cambiarlo por otro.

~~~
python RAG_espanol.ipynb
~~~

3. Crear unha GUI para uno de los RAGs anteriores.

Ejecuta el archivo `GUI_RAG_ingles.ipynb`, luego accede a la URL local de la interfaz Gradio desde navegador.

~~~
python GUI_RAG_ingles.ipynb
~~~

4. RAG dockerizado contra Mongo Atlas.


