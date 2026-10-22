<!-- l10n-sync: source-file="workshop/04-design-vibes.md" -->
# Parte 4: Tematización centrada en el diseño

---

En esta parte, usarás los ciclos de planificación e implementación de Copilot para diseñar una transformación integral del tema. Este es un enfoque de desarrollo centrado en el diseño: empieza con una visión, itera sobre los elementos visuales y deja que Copilot se encargue del trabajo pesado de CSS.

## Tarea 1: Planifica el tema retro

<!-- track:vscode:start -->
Cambia a **Plan** en GitHub Copilot Chat.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Usa `/plan` en GitHub Copilot CLI o pulsa **Shift+Tab** hasta activar el modo plan.
<!-- track:cli:end -->

Introduce este prompt:

> Quiero transformar esta página en una experiencia de arcade retro completa. Planifica una renovación visual integral que incluya: efectos de líneas de barrido CRT en el fondo, un resplandor de neón pulsante en el título, como un letrero de neón, un emblema VS animado con cambios de color en el degradado, una capa de brillo y destellos sobre las tarjetas de resultados de los usuarios, animaciones de entrada flotante para los campos de entrada, texto de carga que cambie de verde a morado y efectos de resplandor al pasar el cursor por los cuadros de contribuciones. Mantén el fondo oscuro (`#0a0a1a`) y los colores de acento verde (`#5fed83`) y morado (`#8a2be2`). Usa un tema oscuro con la fuente retro Press Start 2P de Google Fonts.

Copilot generará un plan de implementación detallado con todos los efectos visuales. **No lo aceptes de inmediato**: revisa el plan e itera:

- Sugiere ajustes en la velocidad de las animaciones (por ejemplo, *«Haz que el pulso de neón sea más lento, de unos 3 segundos»*).
- Pregunta por efectos concretos (por ejemplo, *«¿Cómo funcionará la capa de destellos en las tarjetas?»*).
- Pide cambios en el enfoque si algo no te convence.

## Tarea 2: Implementa el tema

Cuando estés conforme con el plan, pide a Copilot que lo implemente:

> Implementa el plan para el tema de arcade retro que acabamos de diseñar.

Copilot añadirá varias animaciones CSS, pseudoelementos y transiciones a tu hoja de estilos. Esto puede incluir:

- `@keyframes` para líneas de barrido, pulso de neón, destellos y efectos de entrada flotante
- Pseudoelementos (`::before`, `::after`) para los efectos superpuestos
- Propiedades personalizadas de CSS para los colores del tema
- Transiciones y estados al pasar el cursor por los elementos interactivos

<!-- track:cli:start -->
Una vez aplicados los cambios, usa `/diff` para revisar los cambios de estilo antes de aprobarlos.
<!-- track:cli:end -->

## Tarea 3: Perfecciona el estilo

> **⚠️ ¿No ves los cambios?** Si el nuevo tema o las animaciones no aparecen, detén el servidor de desarrollo (`Ctrl+C`), reinícialo con `npm run dev` y actualiza el navegador por completo (`Ctrl+Shift+R`).

Mantén abierta la vista previa del navegador e itera sobre el diseño. Prueba prompts como:

> El efecto de líneas de barrido es demasiado intenso; reduce la opacidad a 0.03.

> Añade un sutil parpadeo eléctrico al texto del título.

> Haz que el emblema VS pulse con más intensidad.

Esto es **desarrollo centrado en el diseño**: iteras sobre el resultado visual en tiempo real. Cada prompt perfecciona la experiencia hasta que tenga el aspecto adecuado. No te conformes con algo «suficientemente bueno»: sigue mejorando el estilo hasta que la página parezca pertenecer a una máquina recreativa.

## Tarea 4: Actualiza las instrucciones

Las instrucciones deben reflejar las principales decisiones de diseño para que los siguientes prompts mantengan el mismo rumbo.

<!-- track:vscode:start -->
Pide a Copilot Chat:

> Añade a `copilot-instructions.md` una sección de guía de diseño que describa el tema de arcade retro: colores, fuentes y estilo de animación.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Pide a Copilot CLI:

> Actualiza las instrucciones del repositorio con una guía breve de diseño para el tema de arcade retro: colores, fuentes, estilo de animación y la regla de que la nueva interfaz debe conservar la estética de neón.
<!-- track:cli:end -->

Cuando la página tenga el aspecto esperado, haz commit de las instrucciones y de los cambios de diseño.

## ✅ Parte 4 completada

**Lo que has aprendido:**

- Usa flujos de planificación para esbozar un **sistema de diseño antes de implementarlo**
- **Itera sobre el resultado visual** con prompts de seguimiento rápidos
- **Actualiza las instrucciones tras tomar decisiones importantes** para que Copilot mantenga la identidad visual
