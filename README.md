# Simulación Monte Carlo: Juego de Serpientes y Escaleras

## Funcionamiento del Código

Este proyecto simula el juego de "Serpientes y Escaleras" utilizando el método de Monte Carlo para analizar el número de turnos necesarios para completar el juego desde diferentes casillas de inicio. El objetivo es calcular el promedio de turnos y el intervalo de confianza para cada casilla, así como observar la convergencia del promedio de turnos desde la casilla 1.

### Proceso de Simulación

1. **Configuración del Tablero:**

   - Se define un tablero con 101 casillas, donde algunas casillas contienen escaleras que permiten avanzar a una posición más alta y serpientes que obligan a retroceder. Estas reglas se configuran en el método `_setup_board` de la clase `Board`.

2. **Simulación de Partidas:**

   - Para cada casilla de inicio (del 1 al 99), se simulan múltiples partidas (hasta 10,000 simulaciones) para calcular el promedio de turnos necesarios para llegar a la casilla 100.
   - Se utiliza un enfoque de paralelización mediante `ThreadPoolExecutor` o `ProcessPoolExecutor`, dependiendo del entorno, para ejecutar las simulaciones de manera concurrente, optimizando así el tiempo de ejecución.

3. **Análisis de Convergencia:**

   - Se realizan simulaciones adicionales desde la casilla 1, variando el número de simulaciones (desde 500 hasta 10,000 en incrementos de 500) para observar cómo converge el promedio de turnos a medida que aumenta el número de simulaciones. Esto se visualiza mediante un gráfico de convergencia.

### Análisis de Resultados

- **Promedio de Turnos y Convergencia:**

  - Desde la casilla 1, el promedio de turnos es 40.15, con un intervalo de confianza del 95% entre 39.66 y 40.64.
  - A medida que se avanza en las casillas, el promedio de turnos disminuye. Por ejemplo, desde la casilla 94, el promedio es de 12.26 turnos, y desde la casilla 96, es de 5.95 turnos.

- **Casillas Estratégicas:**

  - Las casillas con escaleras, como la 4, muestran un aumento en el promedio de turnos debido a la posibilidad de avanzar rápidamente (promedio de 40.36 turnos).
  - Las casillas con serpientes, como la 37, muestran una reducción significativa en el promedio de turnos debido a la penalización de retroceder (promedio de 35.15 turnos).

- **Variabilidad y Precisión:**

  - El intervalo de confianza proporciona una medida de la precisión de las simulaciones. Casillas con un menor número de turnos, como la 96, tienen intervalos de confianza más estrechos, indicando resultados más consistentes.

- **Gráfico de Convergencia:**

  - El gráfico muestra cómo el promedio de turnos desde la casilla 1 se estabiliza alrededor de 39.8 a medida que se incrementa el número de simulaciones, validando la suficiencia de 10,000 simulaciones para obtener resultados confiables.

Este análisis permite entender mejor la dinámica del juego y la influencia de las reglas (escaleras y serpientes) en el resultado final, proporcionando una herramienta educativa y de entretenimiento para explorar probabilidades y estadísticas en un contexto lúdico.
