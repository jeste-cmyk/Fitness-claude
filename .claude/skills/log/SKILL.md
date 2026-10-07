---
name: log
description: Registra un entrenamiento que el usuario describe en texto libre y lo sube a main. Usar cuando el usuario cuente lo que hizo ("hoy hice...", "banca 3x8 60kg", "terminé el bloque A").
---

1. Sincronizar: `git fetch origin main && git checkout main && git pull origin main`.
2. Fecha en Lima: `TZ=America/Lima date '+%Y-%m-%d %A'` salvo que el usuario indique otro día.
3. Archivo: `logs/AAAA/MM/AAAA-MM-DD.md`. Si ya existe, agregar sin borrar lo anterior.
   Sábado: usar secciones `## Bloque A` / `## Bloque B` (preguntar cuál si no queda claro).
4. Formato (una línea por serie o por grupo de series iguales):

   ```
   # 2026-10-03 (sábado)

   ## Bloque A
   - Press banca — 3x8 @ 60 kg — RPE 8, última serie costó
   - Sentadilla — 4x6 @ 80 kg
   - Notas: dormí poco
   ```

   - Nombres de ejercicios consistentes con `rutina/grupos/` (para que grep funcione).
   - Si series distintas: `Press banca — 8/8/6 @ 60 kg`.
   - Guardar sensaciones, dolor, RPE si los menciona. No inventar lo que no dijo.
5. Comparar contra lo planificado (plan de la semana o rutina) y comentar en 1–3 líneas:
   cumplió / superó / quedó corto, y qué implica para la próxima vez según las reglas de CLAUDE.md.
6. `git add logs && git commit -m "log: AAAA-MM-DD <bloque>" && git push origin main`.
7. Confirmar al usuario lo guardado (resumen breve), y si el push falló decirlo claramente.
8. **Cierre del día (preferencia del usuario, 2026-10-07):** si con este log se completó el último grupo
   del día (o del Bloque B en sábado), responder con el **resumen del día** (cada grupo con su resultado
   y una línea de lectura si aplica). **No** hablar de lo que toca mañana ni adelantar el día siguiente.
