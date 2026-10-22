<!-- l10n-sync: source-file="workshop/05-polish.md" -->
# Parte 5: Pulido y trabajo en paralelo

---

Ahora que la aplicación funciona y tiene buen aspecto, es hora de pulirla. En esta parte dividirás el trabajo para mejorar la adaptabilidad, el manejo de errores y la calidad sin hacerlo todo en un único ciclo secuencial.

<!-- track:vscode:start -->
## Tarea 1: Agente en segundo plano para el diseño adaptable

1. En el panel de Chat, haz clic en **+** para iniciar un chat nuevo.
2. En la parte inferior de la ventana, cambia **Local** a **Copilot CLI**.
3. Introduce este prompt:

   ```
   Add responsive CSS media queries: at 1024px switch comparison to single column,
   at 768px reduce font sizes, stack inputs vertically, and make the layout
   mobile-friendly. Also improve keyboard accessibility — ensure tab order works,
   Enter triggers battle, and focus states are visible.
   ```

4. Deja que se ejecute de forma independiente; no hace falta supervisarlo.
5. Cuando termine, **revisa** los cambios y haz clic en **Apply**.

## Tarea 2: Agente en segundo plano para la experiencia de error

1. Inicia otro agente en segundo plano.
2. Introduce este prompt:

   ```
   Improve the error experience: add a shake animation for errors, styled error
   messages with red (#ff3366) neon glow effects matching the arcade theme, and
   better input validation feedback. Show clear error messages when usernames are
   empty or invalid.
   ```

3. Revisa los cambios cuando termine el agente y haz clic en **Apply**.

## Tarea 3: Agente en la nube para probar variaciones (opcional)

1. En el panel de Chat, haz clic en **+** para iniciar un chat nuevo.
2. En la parte inferior de la ventana, cambia **Local** a **Cloud**.
3. Introduce este prompt:

   ```
   Create an alternative color theme for the battle page — keep the retro arcade
   style but use blue (#00f5ff) and orange (#ff6b35) instead of green and purple.
   Create it as a CSS custom property theme that could be toggled.
   ```

4. Consulta las **sesiones de agentes** para supervisar el progreso.
5. Revisa la variación de diseño en el PR que cree el agente en la nube.

## Tarea 4: Comprueba todo
<!-- track:vscode:end -->

<!-- track:cli:start -->
## Tarea 1: Divide el trabajo con `/fleet`

En Copilot CLI, usa `/fleet` para dividir el trabajo entre subagentes en paralelo y después revisa el resultado combinado:

```text
/fleet Improve the app in parallel:
1. Add responsive CSS media queries so the comparison collapses to one column at 1024px and the inputs stack on small screens.
2. Improve keyboard accessibility and focus visibility.
3. Improve the error experience with stronger validation feedback and arcade-style neon error states.
```

Deja que la CLI coordine el trabajo y, después, inspecciona el resultado combinado con `/diff` antes de aprobar cualquier cambio.

## Tarea 2: Delega una variación (opcional)

Si quieres probar un flujo de trabajo asíncrono en la nube, delega una variación de diseño:

```text
/delegate Create an alternative color theme for the battle page that keeps the retro arcade look but swaps in blue (#00f5ff) and orange (#ff6b35). Make it easy to toggle.
```

La tarea delegada debería crear un pull request que puedas revisar por separado mientras sigues trabajando localmente.

## Tarea 3: Ejecuta una revisión agéntica

Antes de terminar, pide a Copilot CLI que revise los cambios:

```text
/review Focus on potential bugs, accessibility issues, and UX regressions in the current branch.
```

Revisa los hallazgos, corrige los que consideres oportunos y vuelve a ejecutar `/diff` para comprobar los cambios.

## Tarea 4: Comprueba todo
<!-- track:cli:end -->

> **⚠️ ¿No ves los cambios?** Si alguna mejora no aparece, detén el servidor de desarrollo (`Ctrl+C`), reinícialo con `npm run dev` y actualiza el navegador por completo (`Ctrl+Shift+R`).

Prueba estos casos para comprobar que todo funciona:

| Prueba | Resultado esperado |
|------|--------------------|
| Campos vacíos y clic en Battle | Error con estilo y animación de sacudida |
| Nombres de usuario válidos | Se muestran los gráficos de contribuciones |
| Nombre de usuario no válido | Error de la API con estilo retro |
| Tecla Enter en un campo | Inicia la batalla |
| Ancho de móvil | Diseño adaptable de una sola columna |
| Pasar el cursor por los cuadros de contribuciones | Información emergente con la fecha y el recuento |

Compila para producción y confirma que no haya errores:

```bash
npm run build && npm run preview
```

Cuando todo tenga buen aspecto, haz commit de los cambios.

---

## ✅ ¡Parte 5 completada!

**Lo que has aprendido:**

- Dividir el trabajo de pulido en **tareas paralelas más pequeñas**
- Revisar los cambios generados antes de incorporarlos a la rama principal
- Usar Copilot para **controles de calidad y experimentos opcionales**, no solo para implementar
