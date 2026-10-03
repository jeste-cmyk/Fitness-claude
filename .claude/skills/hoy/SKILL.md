---
name: hoy
description: Dice qué entrenamiento toca hoy (o el día indicado) con el detalle completo. Usar cuando el usuario pregunte "qué toca hoy", "qué hago hoy", "qué toca mañana" o similar.
---

1. Sincronizar: `git fetch origin main && git checkout main && git pull origin main`.
2. Fecha en Lima: `TZ=America/Lima date '+%Y-%m-%d %A %G-W%V'` (o el día que pidió el usuario).
3. Fuente: si existe `planes/<AAAA-Www>.md` usar el día correspondiente; si no, `rutina/semana.md` para saber qué grupos tocan y `rutina/grupos/<grupo>.md` para el contenido.
   Si es sábado, mostrar Bloque A y Bloque B por separado.
   **Modo uno por uno (preferencia del usuario, 2026-10-03):** mostrar con detalle **solo el primer grupo**
   pendiente de la sesión/bloque (los demás, nombrarlos en una línea como "después: X · Y").
   Cuando el usuario confirme que terminó ese grupo, registrarlo (skill `log`) y mandar el siguiente,
   y así hasta terminar. Orden = el de `rutina/semana.md` (sábado Bloque B: Upper body → Calves → Estirar).
   Si ya hay log de hoy, saltar los grupos ya registrados.
4. Para cada ejercicio buscar el último registro en `logs/` (`grep -rn "<ejercicio>" logs/ | sort | tail`)
   y mostrar "última vez: fecha — resultado".
5. Revisar si ya hay log de hoy (`logs/AAAA/MM/AAAA-MM-DD.md`) y decir qué falta.
6. Responder en formato corto para celular:
   - Título: día, fecha y foco de la sesión
   - Por ejercicio: series x reps @ carga sugerida, descanso, nota técnica breve, última vez
   - Cierre: una línea con el objetivo de la sesión
7. Si algo del día está "por definir", decirlo y ofrecer cargarla.
