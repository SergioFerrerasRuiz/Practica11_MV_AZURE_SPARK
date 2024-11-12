# Ejercicio de Instalación de Apache Spark en una Máquina Virtual de Azure

Este ejercicio tiene como objetivo crear e instalar **Apache Spark** en una **máquina virtual (VM) independiente** en **Azure**, utilizando un sistema operativo **Linux (Ubuntu)**. A lo largo del ejercicio, se aprenderán los pasos necesarios para configurar la máquina virtual, instalar Apache Spark y ejecutarlo en un entorno local.

   ![FTO](assets/1.png)
   ![FTO](assets/2.png)
   ![FTO](assets/3.png)
   ![FTO](assets/4.png)
   Lo demas lo dejamos como esta...

Para ello, nos conectamos a la MV con SSH desde nuestra consola local con gracias a las claves:
```bash
ssh -i "<ruta_a_clavepublica>" <usuario>@<ip_pública>
```
![FTO](assets/5.png)
![FTO](assets/6.png)
Instalamos Java
```bash
sudo apt update
sudo apt install openjdk-8-jdk
```
Comprobamos que se haya instalado bien:
```bash
java -version 
```
![FTO](assets/7.png)
Ahora python
Primero comprobamos si esta instalado
```bash
python --version
```
Si no sale nada, no esta instalado, entonces haremos lo siguiente:
```bash
sudo apt install python3
```

Para descargar spark, vamos a la página de spark para obtener el enlace de la descarga .tgz 
Para descargar spark usamos este comando:
```bash
wget https://downloads.apache.org/spark/spark-3.5.3/spark-3.5.3-bin-hadoop3.tgz
```
![FTO](assets/8.png)
lo probamos poniendo:
```bash
pyspark
```
![FTO](assets/9.png)
o viendo scala con:
```bash
spark-shell
```
![FTO](assets/10.png)
lo descomprimimos:
```bash
tar -xvf spark-3.5.3-bin-hadoop3.tgz
```
y comprobamos con:
```bash
 ls
```
![FTO](assets/11.png)
movemos los archivos a la carpeta /opt/spark y lo comprobamos 
```bash
 sudo mv spark-3.4.5-bin.hadoop3 /opt/spark
 ls /opt/spark
```
 ![FTO](assets/12.png)
editamos el archivo ~/.bashrc para añadir variables de entorno de esta manera:
```bash
nano ~/.bashrc
```
Añadimos lo siguiente dentro del archivo:
 ![FTO](assets/13.png)

Estamos añadiendo la ruta de Spark principal, y la de Java principal
Para guardar los cambios hacemos source ~/.bashrc

Por ultimo paramos y eliminamos la maquina virtual:
 ![FTO](assets/14.png)
 ![FTO](assets/15.png)


