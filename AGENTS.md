# Agent Directives & Specifications: Minijuego Web Tanda de Penaltis

Este documento define las normas técnicas, de arquitectura, diseño UI/UX y mecánicas de juego inmutables para el desarrollo y mantenimiento del minijuego web de Tanda de Penaltis. 

---

## 1. Stack Tecnológico y Arquitectura
- **Archivo único:** Todo el código fuente (HTML5, CSS3, JavaScript vainilla y recursos gráficos/iconos) debe estar contenido estrictamente en un **único archivo `index.html`** optimizado, limpio y comentado.
- **Sin dependencias externas pesadas:** Se permite el uso de librerías por CDN únicamente si son ligeras y esenciales (ej. Tailwind CSS vía CDN para estilos rápidos o fuentes de Google Fonts como *Outfit* o *Inter* para el aspecto deportivo). Se prioriza JavaScript nativo ES6+.
- **Diseño Responsive:** Uso obligatorio de CSS Grid y Flexbox bajo un enfoque Mobile-First adaptado perfectamente a pantallas de escritorio y móviles.

---

## 2. Distribución de Zonas de Tiro (Estrictamente 5 Zonas)
La portería gráfica debe estructurarse obligatoriamente en **exactamente 5 zonas interactivas** con disposición espacial en cruz/esquinas (sin opciones de arriba-centro ni abajo-centro):
1. `TL` (Top-Left): ↖️ **Arriba Izquierda**
2. `TR` (Top-Right): ↗️ **Arriba Derecha**
3. `C` (Center): ⚽ **Centro** (zona central única)
4. `BL` (Bottom-Left): ↙️ **Abajo Izquierda**
5. `BR` (Bottom-Right): ↘️ **Abajo Derecha**

---

## 3. Mecánica Central de Juego y Colisiones
- **Resolución de parada:** Si la zona seleccionada por el lanzador coincide exactamente con la zona elegida por el portero (`zona_lanzador === zona_portero`), el resultado es **PARADA / BLOQUEO**. En caso contrario, es **GOL**.
- **Feedback visual instantáneo:** Animación clara del balón desplazándose hacia la zona elegida y reacción visual del portero tirándose hacia el lado correspondiente con efectos tipográficos dinámicos (ej. "¡GOLAZO!", "¡PARADÓN ESPECTACULAR!").

---

## 4. Modos de Juego Requeridos
1. **Modo 1 Jugador (vs. IA):**
   - *Fase de Lanzamiento:* El usuario hace clic en una de las 5 zonas; la IA selecciona de forma aleatoria (Math.random) una zona para intentar la parada.
   - *Fase de Parada:* La IA selecciona aleatoriamente dónde tira, y el usuario hace clic en una de las 5 zonas para adivinarla e intentar detener el balón.
2. **Modo 2 Jugadores (Local - Mismo equipo / Turnos alternos):**
   - Ronda de penaltis (ej. 5 por jugador o muerte súbita).
   - *Sistema de privacidad de turnos (Pantalla de transición):* Para evitar que el Jugador 2 vea la elección del Jugador 1, se debe mostrar obligatoriamente una pantalla intermedia o de bloqueo ("Pasa el dispositivo al Jugador X") antes de la elección del portero.

---

## 5. UI/UX & Guía de Estilo Visual
- **Estética:** Deportiva, moderna, dinámica y limpia (inspirada en retransmisiones de fútbol profesionales). Uso de gradientes oscuros de césped/estadio, tarjetas translúcidas estilo *glassmorphism* y tipografías geométricas llamativas.
- **HUD y Marcador en Vivo:** Debe mostrar en todo momento:
  - Nombres y colores distintivos de los equipos enfrentados.
  - Puntuación actual (goles anotados / total lanzados o fallados).
  - Indicador de la ronda actual y de quién es el turno activo.
