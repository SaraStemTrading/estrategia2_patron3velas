# ESTRATEGIA2: Patrón de 3 velas en Bollinger
#### Por Sara STEM
>_La bolsa es soberana y se coge el moño donde le da la gana._ - Mi padre.

## Descripción de la estrategia

He programado en Python una estrategia enviada por uno de mis grupos de clase donde, tras un patrón de tres velas rojas tocando la banda inferior de Bollinger, compramos si se produce una vela verde justo después. El stop se mueve a la altura de la media simple de 25 sesiones siempre que el precio haya superado al alza la banda superior de Bollinger. Para el caso bajista es justo al revés.

### Ejemplo de una entrada
!(https://www.sarastem.com/wp-content/uploads/2022/06/entrada_estrategia2.png)
## Instalación previa

Para iniciar este proyecto, debemos tener descargado "Git" y "Python3" en nuestro ordenador. Los podemos encontrar en:
- __Git__: https://git-scm.com/downloads
- __Python3__: https://www.python.org/downloads/

## Terminal

Una vez descargados, abrimos nuestro terminal, y seguimos los siguientes pasos:

1. Entramos en la carpeta donde vamos a alojar el proyecto y escribimos el siguiente código: 

`git clone https://github.com/SaraStemTrading/estrategia2_patron3velas.git`

2. Entramos en la carpeta especificada:

`cd estrategia2_patron3velas`

3. Una vez dentro, desplegamos un entorno virtual del siguiente modo: 

`python -m venv env`

Si no funciona, probamos con:

`python3 -m venv env`

4. Activamos el entorno virtual "env":

En Windows: 

`env\Scripts\activate.bat`

En Mac: 

`source ./env/bin/activate`

Nos fijaremos que estamos dentro del entorno porque aparece __(env)__ en la línea de comandos.

5. Podemos lanzar la aplicación a Visual Studio Code del siguiente modo (aunque también podemos continuar en el terminal): 

`code .` 

## Instalación de dependencias para el proyecto

Completados los pasos anteriores, debemos instalar las dependencias para que la aplicación funcione correctamente.
Esto lo hacemos con la ayuda del archivo __"requirements.txt"__.

Para su instalación, escribimos en el terminal dentro del entorno (ya sea en Visual Studio Code o en el terminal del sistema): 

`pip install -r requirements.txt`

## Archivo .env con los parámetros a rellenar previamente

Este archivo es fundamental para la correcta ejecución de nuestra aplicación, ya que tendrá todos los datos iniciales necesarios. En concreto, son los siguientes parámetros:
- __activo__: Aquí debemos poner entre comillas el ticker del activo al que queremos aplicarle la estrategia y ver el backtesting. Yo he usado el ORO (GC=F). Tienes la lista completa en la web de Yahoo Finanzas, dentro del apartado Mercados, puedes buscar el producto que quieras: https://es.finance.yahoo.com.
- __period__: Esto solo se debe rellenar para datos intradía. Aquí debemos poner entre comillas el periodo de tiempo en el que queremos que nos muestre los datos, y debe inferior a 60 días.
Adjunto imagen con los periodos y timeframes disponibles:
!(https://www.sarastem.com/wp-content/uploads/2022/06/periodsYF.png)
- __interval__: Aquí podremos entre comillas el timeframe que queremos para testear nuestra estrategia.
- __years__: Esto solo sirve para datos en timeframe diarios. Dejaremos un 1 por defecto. Aquí debemos poner el número de años que queremos testear en nuestra estrategia.
- __periodo_bb__: Aquí debemos poner el número de periodos para el cálculo de las bandas de Bollinger, yo lo he hecho por defecto con 20 periodos.
- __periodo_media__: Aquí debemos poner el número de periodos para el cálculo de la media para gestionar el stop. Yo he usado 25 periodos.
- __riesgo_op__: Aquí ponemos el riesgo por operación que queremos asumir. Se pone en tantos por uno. Yo he trabajado con un riesgo del 2% sobre el capital en cada operación.
- __capital__: Aquí ponemos el capital con el que queremos testear nuestra estrategia.
- __comision__: Poner aquí la comisión a aplicar por operación, en tantos por uno. He usado 0,2% en cada operación.
- __margen__: Finalmente, ponemos el margen de apalancamiento, en tantos por uno. En mi caso he usado 1:50, es decir, 0,05.

## Funcionamiento del algoritmo
Una vez rellenados los apartados anteriores, podemos ejecutar el código de nuestra estrategia desde Visual Studio Code y valorar los resultados obtenidos que aparecerán en el terminal de la plataforma.
Recuerda que para probar otros parámetros en esta estrategia, solo debes modificar el archivo .env.

**¡Espero que te resulte de utilidad!**
**Sara STEM**



