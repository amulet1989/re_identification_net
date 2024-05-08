# Entrenar un modelo de Re identificación utilizando. Utilizando Tao-toolkit.
## Descripción

Un modelo Reidentification genera embeddings para identificar objetos capturados en diferentes escenas.

El modelo es esencialmente un backbone de Deep Learning que toma imágenes recortadas de objetos como entrada y produce embeddings de características como salida.

- Algoritmo de entrenamiento
El algoritmo de entrenamiento optimiza la red para minimizar la pérdida de entropía triple, central y cruzada.

- Caso de uso previsto
El caso de uso principal previsto para este modelo es generar embeddings para un objeto y luego realizar coincidencias de similitud entre incrustaciones de diferentes escenas.

## Instalación de tao toolkit
Se desarrolló el siguiente paso paso para  instalar las dependencias necesarias para levantar los toolbox de entrenamientos de Tao-toolkit e un servidor local ubuntu.

Descargar el paquete NGC get_started.

```
wget --content-disposition https://api.ngc.nvidia.com/v2/resources/nvidia/tao/tao-getting-started/versions/5.2.0/zip -O getting_started_v5.2.0.zip
unzip -u getting_started_v5.2.0.zip -d ./getting_started_v5.2.0 && rm -rf getting_started_v5.2.0.zip && cd ./getting_started_v5.2.0
```
Se necesita tener instalado Docker [(Install Docker Engine)](https://docs.docker.com/engine/install)

Instalar nvidia-container-toolkit [(Installing the NVIDIA Container Toolkit — NVIDIA Container Toolkit 1.15.0 documentation )](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html)

Obtenga una cuenta NGC y una clave API si no se tiene [(GPU-optimized AI, Machine Learning, & HPC Software | NVIDIA NGC )](https://ngc.nvidia.com/):

Inicie sesión en el registro Docker de NGC [(nvcr.io)](http://nvcr.io/) utilizando el comando “docker login nvcr.io” e introduzca las siguientes credenciales: 

```
username: $oauthtoken

password: <my api key>
```
donde <my api key> corresponde a la clave que generó con la cuanta NGC.

### Generar un entorno virtual usando Conda con una versión de python superior o igual a la 3.7.
```
conda create -n launcher python=3.7

conda activate launcher
```
### Instalación del lanzador TAO
Después de haber instalado los requisitos previos requeridos:

Instale el iniciador CLI utilizando el script de inicio rápido descargado con el paquete NGC get_started.
```
bash setup/quickstart_launcher.sh --install
``` 

Utilice este script para actualizar el iniciador a la última versión de TAO Toolkit ejecutando el siguiente comando:


```
bash setup/quickstart_launcher.sh --upgrade
```

### Instalar jupyter para poder utilizar los notebooks demos de Tao.
```
pip3 install notebook
```
Luego levantar un servidor de jupyter notebook o simplemente ejecutar cualquiera de los cuadernos de código dentro del VScode.
```
jupyter notebook --ip 0.0.0.0 --port 8888 --allow-root --NotebookApp.token=<un token>
```
 
Una vez realizados todos estos pasos Tao-toolkit ya se encontrará disponible para ejecutarse en nuestro servidor. La mayoría de los pasos anteriores se realizan por una única vez. Cuando terminemos solo debemos desactivar el entorno virtual y para continuar activarlo usando
```
conda activate launcher
```
Abrir el notebook o script de python necesario y poner a correr. 

Estos modelos rentrenados podrán ser perfectamente incorporados a los pipelines de Deepstream o subidos a Tritón paras realizar las inferencias.

Cualquier otra duda se podrá solventar dentro del set de tutoriales [TAO Toolkit](https://docs.nvidia.com/tao/tao-toolkit/index.html) 