<!-- l10n-sync: source-file="workshop/06-bonus.md" -->
# 🎉 Bonus y Extensiones

---

¡Has construido una aplicación de GitHub Battle completamente funcional! Ahora es momento de ir más allá con **desafíos abiertos**.

<!-- track:vscode:start -->
Usa **Agent Mode** para todos estos — describe lo que quieres y deja que Copilot te ayude a construirlo.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Usa Copilot CLI para todos estos — combina contexto con `@file`, `/plan`, modo normal y `/review` según sea necesario.
<!-- track:cli:end -->

---

## 🏆 Desafío 1: Banner de Ganador

Después de que ambos gráficos de contribuciones carguen, compara los totales y muestra un anuncio dinámico del ganador.

**Qué construir:**
- Compara las contribuciones totales de ambos usuarios
- Muestra **"🏆 {username} GANA 🏆"** con un estilo de celebración si hay un ganador claro
- Muestra **"🤝 ¡EMPATE! 🤝"** si las contribuciones son iguales
- Agrega animación o confeti para más efecto

**Sugerencia de prompt:**
> Cuando se carguen los datos de contribuciones de ambos usuarios, compara los totales y muestra un anuncio del ganador. Muestra «🏆 {username} GANA 🏆» si un usuario tiene más contribuciones o «🤝 ¡EMPATE! 🤝» si tienen la misma cantidad. Dale un aspecto llamativo con animaciones CSS.

---

## 🏆 Desafío 2: Contador de Racha

Calcula y muestra la racha de contribuciones consecutivas más larga de cada usuario.

**Qué construir:**
- Analiza los datos de contribuciones día por día
- Encuentra la serie más larga de días consecutivos con al menos una contribución
- Muestra el conteo de la racha de forma prominente para cada usuario
- Resalta quién tiene la racha más larga

**Sugerencia de prompt:**
> Añade un contador de rachas que analice los datos de contribuciones de cada usuario y encuentre su racha más larga de días consecutivos. Muestra «🔥 Racha más larga: X días» debajo del gráfico de contribuciones de cada usuario.

---

## 🏆 Desafío 3: Historial de Batallas

Persiste los resultados de las batallas para que los usuarios puedan ver sus enfrentamientos anteriores.

**Qué construir:**
- Guarda cada resultado de batalla en `localStorage` (nombres de usuario, totales, ganador, marca de tiempo)
- Agrega una sección **"Batallas recientes"** debajo del área principal de batalla
- Muestra las últimas 5–10 batallas con resultados
- Agrega un botón "Borrar historial"

**Sugerencia de prompt:**
> Guarda los resultados de cada comparación en `localStorage`. Añade una sección «Batallas recientes» con las últimas 10 batallas, los nombres de usuario, los totales de contribuciones, el ganador y la fecha. Incluye un botón «Borrar historial».

---

## 🏆 Desafío 4: Efectos de Sonido

Agrega efectos de sonido retro arcade usando la Web Audio API — sin necesidad de archivos externos.

**Qué construir:**
- Sonido de **insertar moneda** cuando se hace clic en el botón "¡Batalla!"
- Sonido de **subida de nivel** cuando los resultados se cargan correctamente
- Sonido de **explosión** cuando ocurre un error (usuario no encontrado, fallo de API)
- Un botón de alternancia para silenciar/activar sonido

**Sugerencia de prompt:**
> Añade efectos de sonido de arcade retro con la Web Audio API (sin archivos de audio). Reproduce un sonido de moneda al iniciar una batalla, un sonido de mejora de poder al cargar los resultados y un sonido de explosión cuando haya errores. Genera los sonidos mediante código con osciladores y nodos de ganancia. Incluye un botón para silenciar el audio.

---

## 🏆 Desafío 5: Secuencia de Batalla Animada

Crea suspenso con una cuenta regresiva dramática antes de revelar los resultados.

**Qué construir:**
- Cuando se haga clic en "¡Batalla!", muestra una superposición a pantalla completa
- Anima: **"3..."** → **"2..."** → **"1..."** → **"⚡ ¡A LUCHAR! ⚡"**
- Luego revela los gráficos de contribuciones con una entrada dramática
- Usa animaciones CSS o temporización con JavaScript

**Sugerencia de prompt:**
> Añade una secuencia animada de batalla al hacer clic en «¡Battle!». Muestra una cuenta atrás superpuesta: «3...», «2...», «1...» y «⚡ ¡A LUCHAR! ⚡», con una duración aproximada de 1 segundo por paso. Después de la cuenta atrás, muestra los resultados con una animación deslizante.

---

## 🏆 Desafío 6: Leyenda de Contribuciones

Agrega una leyenda de escala de colores que coincida con la paleta de colores del gráfico de contribuciones.

**Qué construir:**
- Una leyenda horizontal mostrando los niveles de intensidad de contribuciones
- Etiquetas desde **"Menos"** hasta **"Más"**
- Usa la paleta de colores real de la respuesta de la API de contribuciones de GitHub
- Posiciónala cerca de los gráficos de contribuciones

**Sugerencia de prompt:**
> Añade debajo de los gráficos una leyenda de contribuciones que muestre la escala de colores de la paleta de la API. Muestra una fila de cuadros de color, de «Menos» (el más claro) a «Más» (el más oscuro), con los colores reales de los niveles de contribución que devuelve la API.

---

## 🏆 Desafío 7: Compartir Resultados

Permite que los usuarios compartan sus resultados de batalla con un solo clic.

**Qué construir:**
- Un botón **"📋 Compartir resultados"** que aparece después de una batalla
- Copia un resumen de texto formateado al portapapeles
- Incluye nombres de usuario, totales de contribuciones y el ganador
- Muestra brevemente el mensaje de confirmación "¡Copiado!"

**Sugerencia de prompt:**
> Añade un botón «📋 Compartir resultados» que copie al portapapeles un resumen de la batalla con formato. El resumen debe incluir ambos nombres de usuario, sus totales de contribuciones y quién ganó. Usa la API del portapapeles y muestra brevemente «¡Copiado al portapapeles!».

---

<!-- track:cli:start -->
## 💻 Extras del CLI

Si quieres explorar más funcionalidades de Copilot CLI después del taller principal:

- Usa `copilot -p "Write a conventional commit message for the current git diff"` para generar una respuesta rápida de un solo disparo que puedes pegar en Git.
- Ejecuta `/share file` para guardar tu sesión como Markdown para referencia futura.
- Usa `/session` y `/session plan` para inspeccionar cómo el CLI está rastreando tu trabajo actual.
<!-- track:cli:end -->

## 🎊 ¡Felicitaciones!

¡Has completado el taller **Mona Mayhem: GitHub Battle**! Esto es lo que lograste:

### Lo Que Construiste

- ✅ Una **aplicación web completa de múltiples páginas** a partir de una especificación de diseño
- ✅ Una **página de inicio** con temática retro arcade y diseño responsivo
- ✅ Una **arena de batalla** que obtiene y compara datos reales de contribuciones de GitHub
- ✅ **Gráficos de contribuciones interactivos** con niveles de actividad codificados por colores
- ✅ **Manejo de errores, estados de carga y mejoras de accesibilidad**
- ✅ **Diseño responsivo** que funciona en todos los dispositivos

### Lo Que Practicaste

| Habilidad | Lo Que Practicaste |
|-----------|-------------------|
| **Context Engineering** | Darle a Copilot los archivos, instrucciones y restricciones correctas |
| **Planificación** | Generar y refinar planes de implementación antes de programar |
| **Codificación Agéntica** | Delegar trabajo en múltiples archivos y múltiples pasos a Copilot |
| **Iteración de Diseño** | Comenzar desde una dirección visual y refinar hacia un resultado pulido |
| **Disciplina de Revisión** | Inspeccionar cambios generados por IA antes de hacer commit |

### 🚀 Sigue Adelante

- 📺 [Canal de YouTube de VS Code](https://www.youtube.com/@code) — Tips, tutoriales y novedades
- 📖 [Documentación de GitHub Copilot](https://docs.github.com/en/copilot) — Documentación oficial y guías
- 💻 [Documentación de GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli) — Instalación, comandos slash y mejores prácticas
- 🌟 [Awesome GitHub Copilot](https://github.com/stefanprodan/awesome-github-copilot) — Recursos y ejemplos de la comunidad
- 🛠️ [Talleres de Copilot Dev Days](https://github.com/github/copilot-dev-days) — Más talleres prácticos como este

---

## 🙏 ¡Gracias!

¡Gracias por unirte a este taller! Has experimentado cómo GitHub Copilot puede acelerar cada fase del desarrollo — desde la planificación y el diseño hasta la implementación y el pulido. Las técnicas que practicaste aquí se aplican a cualquier proyecto, cualquier framework y cualquier escala. ¡Ahora ve y construye algo increíble! 🚀
