Análisis de Ensayo de Tracción

Este script en Python calcula y grafica los resultados de un ensayo de tracción de una probeta (rectangular o circular), a partir de datos experimentales de fuerza y desplazamiento (delta).

¿Qué hace el programa?


Lee los datos de un archivo de texto llamado Datos_Probeta.txt, que debe tener dos secciones: una llamada Fuerza y otra llamada Delta, cada una con una lista de valores numéricos.
Pide al usuario que elija el tipo de probeta (rectangular o circular) y que ingrese sus medidas (longitud, ancho, espesor o diámetro, tanto iniciales como finales).
Calcula, entre otras cosas:

Área inicial y final de la probeta
Deformación unitaria (ingenieril y real)
Esfuerzo (ingenieril y real)
Energía de deformación
Módulo de Young (por mínimos cuadrados)
Límite de fluencia
Resistencia a la tracción y punto de rotura
Resiliencia y tenacidad
Porcentaje de elongación y de estricción



Grafica:

La curva de esfuerzo vs. deformación (real e inicial), marcando los puntos máximos.
El ajuste lineal usado para obtener el módulo de Young.





Requisitos


Python 3
Librerías: numpy, matplotlib


Instalación rápida:

pip install numpy matplotlib

Archivo de datos necesario

Debes tener un archivo llamado Datos_Probeta.txt en la misma carpeta que el script, con este formato:

Fuerza
100.5
200.3
300.1
...

Delta
0.01
0.02
0.03
...

Cómo usarlo


Coloca Datos_Probeta.txt junto al script.
Ejecuta el script:


   python nombre_del_script.py


Selecciona el tipo de probeta (1 = rectangular, 2 = circular).
Ingresa las medidas que te vaya pidiendo (longitudes, ancho, espesor o diámetro).
El programa mostrará en pantalla todos los resultados calculados y luego abrirá dos gráficas.


⚠️ Cosas a tener en cuenta (errores en el código)

Antes de usarlo, hay algunos errores que probablemente impidan que funcione correctamente, sobre todo en la opción de probeta circular:


En la función Calculoc, se usa math.pi(d1) ^ 2, lo cual no es válido en Python (esto da error). Debería ser algo como (math.pi * d1**2) / 4. Además, ^ en Python es un operador distinto a "elevado a la potencia" (para eso se usa **).
La función Calculoc recibe 6 parámetros (d1, d2, w, e, ef, wf) pero en el código se llama solo con 5 (Calculoc(Dc, Df, e, ef, wf)), lo que también causará un error.
Dentro de Calculoc, se usan w y wf para calcular ey, pero como esos parámetros no llegan bien (ver punto anterior), esto fallará.


En resumen: la ruta de probeta rectangular (opción 1) debería funcionar bien, pero la ruta de probeta circular (opción 2) necesita corregirse antes de poder usarla. Si quieres, puedo ayudarte a corregir esa parte del código.
