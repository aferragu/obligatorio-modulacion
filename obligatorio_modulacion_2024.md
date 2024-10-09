# Propagación y Modulación

## Trabajo Obligatorio - Curso 2024.

En este trabajo obligaotrio, se busca analizar el comportamiento de diferentes señales digitales, tanto en banda base como en radio frecuencia, con diferentes formas de pulso y codificación de canal. Para ello, trabajaremos con el software [`gnuradio`](https://www.gnuradio.org/). Este software permite trabajar con señales en tiempo real, y dispone de numerosos bloques para filtrar, modular, etc.

A su vez, permite trabajar con interfaces de radio SDR, como por ejemplo [ADALM-PLUTO](https://www.analog.com/en/resources/evaluation-hardware-and-software/evaluation-boards-kits/adalm-pluto.html).


### Ejercicio 1 (Espectro de la onda PAM, diagrama de ojo)

Considere el diagrama de bloques de ejemplo `digital_baseband.grc`. Allí, se provee un generador de bits aleatorios equiprobables. Al repetirlo `sps=16`, generamos una señal digital con 16 muestras por símbolo, cuyo pulso es NRZ. La frecuencia de muestreo se establece en $f_0=32$ kHz, por lo que la frecuencia de símbolo es $f_0/sps=f_s = 2$ kHz. La señal se alimenta a un filtro pasabajos, que opera como canal de ancho de banda $B$ ajustable, y se le agrega ruido gaussiano de desvío estándar $\sigma_N$ ajustable.

1. Observe el espectro de la señal enviada. ¿Puede identificarlo con el espectro de la onda PAM NRZ unipolar?
2. Muestre cómo se modifica el diagrama de ojo al cambiar la potencia del ruido y el ancho de banda del canal.
3. Modifique el diagrama de bloques para que el pulso sea de tipo RZ, con ancho medio tiempo de símbolo. Muestre cómo cambia el ancho de banda requerido y muestre si aparecen señales de sincronismo.
4. Modifique el diagrama de bloques para usar ahora codificación bipolar y pulso RZ. ¿Qué cambia en los diagramas?
5. Modifique el diagrama de ojo para usar un pulso Manchester:
   $$p(t) = \begin{cases}
                \mathbf{1}_{[0,T_s/2]}(t) - \mathbf{1}_{[Ts/2,T_s]}(t) & \textrm{si } a_k=1 \\ 
                -\mathbf{1}_{[0,T_s/2]}(t) + \mathbf{1}_{[Ts/2,T_s]}(t) & \textrm{si } a_k=0.
                \end{cases}$$ 
    Muestre el espectro de esta señal y observe que no tiene componente de baja frecuencia.


### Ejercicio 2 (Transmisión en banda base con pulso acoplado)



### Ejercicio 3 (Transmisión QPSK con pulso RRC)