---
name: hoy
description: Dice qué entrenamiento toca hoy (o el día indicado) con el detalle completo. Usar cuando el usuario pregunte "qué toca hoy", "qué hago hoy", "qué toca mañana" o similar.
---

1. Sincronizar: `git fetch origin main && git checkout main && git pull origin main`.
2. Fecha en Lima: `TZ=America/Lima date '+%Y-%m-%d %A %G-W%V'` (o el día que pidió el usuario).
3. Fuente: si existe `planes/<AAAA-Www>.md` usar el día correspondiente; si no, `rutina/actual.md`.
   Si es sábado, mostrar Bloque A y Bloque B por separado.
4. Para cada ejercicio buscar el último registro en `logs/` (`grep -rn "<ejercicio>" logs/ | sort | tail`)
   y mostrar "última vez: fecha — resultado".
5. Revisar si ya hay log de hoy (`logs/AAAA/MM/AAAA-MM-DD.md`) y decir qué falta.
6. Responder en formato corto para celular:
   - Título: día, fecha y foco de la sesión
   - Por ejercicio: series x reps @ carga sugerida, descanso, nota técnica breve, última vez
   - Cierre: una línea con el objetivo de la sesión
7. Si la rutina está vacía o pendiente, decirlo y ofrecer cargarla.
