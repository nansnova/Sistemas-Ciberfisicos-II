# Sistemas-Ciberfisicos-II
## Autores
Este proyecto fue desarrollado por:
- Abril Berenice Bautista Román
- Luis Eduardo Ávila Gómez
- Mariel Alquisira Morales
- Nancy L. García Jiménez

## Acerca
Este repositorio contiene el código fuente, los esquemáticos de conexión, los modleos CAD en formato de edición de fusion y tipo objeto necesarios para el desarrollo de 3 propuestas para una futura implementación en la fábrica de tornillos Forjadora Panamericana, S.A. De C.V.
- En la maquina ranuradora, se implementó un prototipo para la detección del estado del herramental usado para el grabado de la figura del cabezal de los tornillos, esto utilizando un clasificador de red neuronal convolucional de 2 clases.
- En la maquina forjadora se implementó un sistema de cómputo en la nube que incluye una interfaz en línea de un contador de los tornillos producidos y una alarma de detección de atasco.
- Finalmente utilizando las medidas reales de la roladora se modeló un gemelo digital utilizado en una propuesta de realidad virtual y otra de realidad aumentada.

## Hardware utilizado
Para el primer proyecto se utilizó:
- Como microcontrolador un arduino uno.
- Como actuador un servo motor con tope de 180.
- Un sistema de biela manivela cortada en mdf y otras partes impresas en 3D. 
- Cámara Raspberry Pi para la parte de visión computacional.
<br>
<a href="url"><img src="computo_cognitivo/prototipo.png" align="center"></a>
<a href="url"><img src="computo_cognitivo/prototipo_digital.png" align="center" height="300" width="300" ></a>
<a href="url"><img src="computo_cognitivo/prototipo_digital_2.png" align="center" height="300" width="300" ></a>
<br>
<br>
<br>
En el segundo proyecto se diseñó el siguiente circuito para el acondicionamiento de señal del sensor analogico inductivo M30 de uso industrial, de la empresa contrinex, acceder al siguiente enlace para más información:
https://www.tme.com/mx/es/details/dwas603m30002/sensores-de-induccion-cilindricos-cc/contrinex/dw-as-603-m30-002/ <br>
- Como microcontrolador un ESP32<br>
- Para el circuito de acondicionamiento un amplificador operacional UA741CD, un transistor 2N2222 y resistencias de diferentes valores
<br>
<br>
<a href="url"><img src="computo_en_la_nube/sensor_inductivo.png" align="center" height="300" width="300" ></a>
<a href="url"><img src="computo_en_la_nube/esquematico.png" align="center"></a>
<a href="url"><img src="computo_en_la_nube/circuito.png" align="center"></a>
<a href="url"><img src="computo_en_la_nube/fenolica_final.jpeg" align="center" height="300" width="300" ></a>
<br>
<br>
Finalmente el gémelo digital se modelo apartir de las medidas y mecanismos de la roladora real que se encuentra en la fábrica, se utilizó el software Fusion360.
<br>
<br>
<a href="url"><img src="manufactura_inteligente/roladora_real.png.jpg" align="center" height="300" width="300" ></a>
<a href="url"><img src="manufactura_inteligente/roladora_digital.png" align="center"  height="300" width="300" ></a>
<a href="url"><img src="manufactura_inteligente/fusion360.png" align="center" height="150" width="150" ></a>
<br>
<br>
En el siguiente enlace se puede visualizar el resultado final de los render generados en fusion 360:
https://www.youtube.com/watch?v=eVM0RRYKtTc
<br>
<br>
Utilizando los componenetes modelados se introdujeron al entorno de Vuforia para desarrollar una experiencia de Realidad Aumentada (AR) que permite, a través de una aplicación de celular escanear el área y desplegar las piezas modeladas en fusion360, finalmente fue posible simular los mecanismos escribiendo el código de movimiento en javascript.
<br>
Los resultados se pueden ver en el siguiente enlace: 
https://drive.google.com/file/d/1TVXQTSXJNs7vJ0RBuuq5s9oS23s3zATd/view?usp=drivesdk
<br>
<br>
<a href="url"><img src="manufactura_inteligente/roladora_vuforia.png" align="center" ></a>
<a href="url"><img src="manufactura_inteligente/vuforia_logo.png" align="center"></a>
<br>
La hoja de especificaciones tecnicas se encuentra dentro de la carpeta de computo_en_la_nube como *DW-Ax-509-M30-3x0*

### Qué códigos usar
- Para el microcontrolador conectado al prototipo del primer proyecto ir a la carpeta **computo_cognitivo**, usar el codigo **servo_180.ino**.
- **socket_client.py** en raspberry pi con la cámara y OpenCV previamente configurados. Revisar la dirección IP y puertos para establecer la conexión.
- **socket_server.py** en la computadora en la que se crea el servidor, utilizar la IP de este dispositivo y crear una carpeta test para guardar la imágen. 
- Las modificaciones a la arquitectura de la red se deben hacer en el entrenamiento del archivo **RED NEURONAL PARA LA DETECCIÓN DE DADOS DAÑADOS.ipynb**
- Y una vez que se tiene todo lo demás activo, utilizar **classify.py** de la carpeta testing en computo_cognitivo.
- Para la implementación del dashboard en Home Assistant usar **dashboard_home_assistant.yaml** y seguir el manual **manual_home_assistant.pdf** de la carpeta computo_cognitivo para la creación de helpers y automatizaciones para la configuración del ambiente.

## Referencias
Para más referencias sobre el funcionamiento de vuforia y Home Assistante, por favor siga los tutoriales descritos en el manual **Reporte Final** de la página de inicio del repositorio
