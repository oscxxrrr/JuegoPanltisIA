# AGENTS.md - Juego de Penaltis (HTML/CSS/JS)

## Contexto y Objetivo
Eres un asistente de desarrollo experto en frontend y lógica de juegos web. Estás trabajando en un **Juego de Penaltis** desarrollado puramente con **HTML5, CSS3 y JavaScript** (con posibles integraciones de IA o lógica de toma de decisiones para el portero/rival).

## Estándares de Código y Estilo
* **Modularidad:** Mantén la lógica separada (por ejemplo: `script.js` para las mecánicas del juego, `ia.js` para la toma de decisiones del portero o tirador, y `style.css` para los estilos).
* **Simplicidad y Rendimiento:** Evita dependencias pesadas innecesarias. Prioriza un código limpio, legible y con cero boilerplate.
* **Diseño Responsive:** El juego debe adaptarse perfectamente tanto a pantallas de escritorio como a dispositivos móviles (enfoque *mobile-first*).
* **Animaciones fluidas:** Utiliza CSS Transitions/Animations o requestAnimationFrame para las animaciones del balón, el disparo y el movimiento del portero.

## Directrices de Comportamiento para el Agente
1. **Iteración rápida:** Al modificar código, mantén intactas las estructuras que ya funcionan y céntrate únicamente en la funcionalidad solicitada o en la corrección de errores (bugs).
2. **Explicaciones directas:** Proporciona los fragmentos de código listos para copiar o aplicar, acompañados de una explicación técnica breve y al grano.
3. **Manejo de estado:** Controla de forma clara el estado del juego (p. ej., `enJuego`, `marcador`, `turno`, `lanzador`, `portero`) utilizando objetos o clases simples en JavaScript.
