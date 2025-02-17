# Simulación Monte Carlo: Juego de Serpientes y Escaleras

## Funcionamiento del Código

Este proyecto simula el juego de "Serpientes y Escaleras" utilizando el método de Monte Carlo para analizar el número de turnos necesarios para completar el juego desde diferentes casillas de inicio. El objetivo es calcular el promedio de turnos y el intervalo de confianza para cada casilla, así como observar la convergencia del promedio de turnos desde la casilla 1.

### Proceso de Simulación

1. **Configuración del Tablero:**

   - Se define un tablero con 101 casillas, incluyendo escaleras y serpientes que alteran la posición del jugador.

2. **Simulación de Partidas:**

   - Para cada casilla de inicio (del 1 al 99), se simulan múltiples partidas (2000 simulaciones) para calcular el promedio de turnos necesarios para llegar a la casilla 100.
   - Se aplica un enfoque de paralelización para ejecutar las simulaciones de manera concurrente, optimizando el tiempo de ejecución.

3. **Análisis de Convergencia:**
   - Se realizan simulaciones adicionales desde la casilla 1, variando el número de simulaciones (500, 1000, 1500, 2000) para observar cómo converge el promedio de turnos a medida que aumenta el número de simulaciones.

### Análisis de Resultados

- **Promedio de Turnos:**

  - El promedio de turnos para cada casilla proporciona una medida de la dificultad relativa de comenzar desde diferentes posiciones en el tablero.
  - Las casillas con acceso temprano a escaleras tienden a tener un menor promedio de turnos.

- **Intervalo de Confianza:**

  - El intervalo de confianza al 95% ofrece una estimación de la variabilidad en el número de turnos, indicando la precisión de las simulaciones.

- **Convergencia:**
  - El gráfico de convergencia para la casilla 1 muestra cómo el promedio de turnos se estabiliza a medida que se incrementa el número de simulaciones, lo que valida la suficiencia del número de simulaciones para obtener resultados confiables.

Este análisis permite entender mejor la dinámica del juego y la influencia de las reglas (escaleras y serpientes) en el resultado final, proporcionando una herramienta educativa y de entretenimiento para explorar probabilidades y estadísticas en un contexto lúdico.
