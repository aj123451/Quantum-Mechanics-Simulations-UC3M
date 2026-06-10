# ⚛️ Simulaciones de Nanoestructuras y Mecánica Cuántica

Este repositorio contiene las resoluciones computacionales desarrolladas para el Laboratorio de Mecánica Cuántica Avanzada. El proyecto explora numéricamente dos fenómenos fundamentales de la mecánica cuántica aplicada a dispositivos de estado sólido: el efecto túnel resonante en heteroestructuras y la cuantización de órbitas electrónicas (niveles de Landau) bajo campos magnéticos.  

## 🎯 El Reto

El desafío principal consistía en modelar computacionalmente sistemas cuánticos complejos, partiendo de los principios de la ecuación de Schrödinger, para observar comportamientos no intuitivos de la materia:

- **Efecto Túnel Resonante:** Calcular el coeficiente de transmisión de un electrón a través de un potencial de doble barrera. Debíamos demostrar numéricamente cómo la probabilidad de transmisión alcanza la unidad perfecta cuando la energía del electrón coincide con los estados cuánticos del pozo, y cómo esta resonancia se ve afectada al introducir asimetrías o sesgos externos.  
- **Niveles de Landau:** Simular el movimiento de un electrón orbitando bajo un campo magnético estacionario. Usando el gauge de Landau, el problema se transforma en un oscilador armónico cuántico desplazado. El gran reto era calcular computacionalmente estados altamente excitados para visualizar la convergencia entre la mecánica cuántica y la física clásica.  

## 🚀 Nuestra Implementación Numérica

Desarrollamos algoritmos enfocados en la estabilidad computacional y la fidelidad física, evitando simuladores de "caja negra":

### 1. Dinámica de Transmisión (Doble Barrera GaAs/GaAlAs)
Implementamos el modelado del coeficiente de transmisión utilizando la masa efectiva del electrón (0.067 me) tanto para los pozos de GaAs como para las barreras de GaAlAs.  

* **El Caso Simétrico:** Localizamos las energías de resonancia exactas para una estructura teórica con barreras de 1 eV.  
* **El Caso Asimétrico (Estructural):** Computamos el sistema enfrentando al electrón a barreras desiguales (0.5 eV frente a 1.13 eV), evaluando la degradación del efecto túnel.  
* **Sesgo Externo (Aplicación de Campo):** Modelamos un campo eléctrico uniforme a lo largo de la estructura, introduciendo una caída de potencial de -0.63 eV en la barrera derecha respecto a la izquierda, simulando así las condiciones operativas de un diodo túnel real.  

### 2. Generación Recursiva de Estados de Landau
Para evitar el desbordamiento de memoria (overflow) y la inestabilidad que supone calcular factoriales o polinomios de Hermite inmensos desde cero, diseñamos un enfoque iterativo:

* **Algoritmo de Recurrencia:** Utilizamos las funciones de onda del estado fundamental y el primer estado excitado como semillas matemáticas. A partir de ahí, aplicamos una relación de recurrencia robusta para generar los estados de índice superior de forma secuencial.  
* **El Límite Clásico:** Computamos y graficamos exitosamente la función de onda y la densidad de probabilidad extrema para los niveles n=18, n=50 y n=100.  

## 🛠️ Tecnologías Utilizadas

* **[Python / MATLAB]:** Como motor principal para la resolución numérica, la iteración espacial y la gestión de recurrencias. *(Nota: Cambia al que hayas usado y borra el otro)*
* **[Numpy / Scipy]:** Para la vectorización masiva de las funciones de onda sobre miles de puntos espaciales y el cálculo de números complejos.
* **[Matplotlib]:** Creación de visualizaciones gráficas avanzadas para interpretar densidades de probabilidad y espectros de transmisión.

## 🏆 Logros Destacados

- **Demostración del Principio de Correspondencia:** En la simulación del nivel de Landau n=100, se observa perfectamente cómo la densidad de probabilidad cuántica "imita" a la clásica, acumulando la mayor probabilidad en los puntos de retorno (los bordes del oscilador), validando la teoría física a nivel numérico.  
- **Flexibilidad del Solver:** El código de transmisión es capaz de resolver cualquier perfil de potencial arbitrario, asimilando saltos abruptos o gradientes continuos (como los introducidos por el sesgo eléctrico).

## 👥 Autor

**[Tu Nombre]** - [GitHub](https://github.com/TuUsuario) | [LinkedIn](https://linkedin.com/in/TuPerfil)

> *Prácticas desarrolladas para el Quantum Laboratory - Physics Department.*
