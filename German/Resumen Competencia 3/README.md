En este repositorio encontrará el resumen de los archivos utilizados para generar la mejor salida para salida kaggle. **A tener en cuenta**:

- En el archivo **"(Comp_3)VM_Clase_Ternaria_SQL_(clase_13).ipynb"** realicé el _feauture engineering_ del dataset "crudo", a través de SQL. A modo de resumen en todas las variables: realicé los Lags 1, 3, 6; el Delta 1; la media móvil de 6 meses; tendencia lineal de 7 meses; agregué la columna 'total_mcaja' como la suma de mcaja_ahorro'+'mcuenta_corriente' +'minversiones1'+minversiones2'+'mcaja_ahorro_adicional'+'mcaja_ahorro_dolares'+'mcuenta_corriente_adicional'+'mcuentas_saldo'+'mcuenta_debitos_automaticos"; y saqué las columnas con más de 50% de nulos. Quedaron arriba de 1000 columnas. Asimismo, hice la siguiente selección de meses (la máxima posible, excluyendo pandemia):

  ![image](https://github.com/germanpestchanker/dmeyf2023/assets/142175027/2fcbc0da-5b80-4737-91ce-a3de1d48961e)

- Luego, en el archivo **"(Clase_13)_BO_Lgbm.ipynb"**, sobre ese nuevo dataset procesado, realicé una Optimización Bayesiana con la semilla "279511" (la primera elegida en el _check in_ de la materia), que demoró aproximadamente 6 días en una máquina virtual de 256 gb de RAM. Las 66 iteraciones se encuentran en el archivo **"BO_log clase 13.txt"**.

- En script **"(Clase_14)_Semillerío.ipynb"**, con los parámetros de la mejor ganancia de los logs del paso anterior, hago 100 modelos iguales pero con distintas semillas. En este paso tardé aproximadamente 5 días.

- En el script **"(Clase_14)_Ensemble_Semillerío.ipynb"**, realizo el promedio de las 100 probabilidades obtenidas en el semillerío, para mejorar el promedio y reducir la varianza de scores. También se generan las salidas para kaggle entre 8000 y 15000 envíos, de a 500. Termino eligiendo el envío de 10.000, ya que la meseta de los scores de kaggle público en este y otros intentos consistemente se hace entre los 9000 y 10000 envios (ver los archivos **"Performance exp colaborativos (clase 13).xlsx" y "Performance clase 14.xlsx"** para más detalles) que está más cerca de los óptimos de la salida bayesiana (arriba de los 11.000).
