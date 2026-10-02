---
name: plan-semana
description: Genera el plan de la semana siguiente (o la indicada) con cargas concretas a partir de la rutina y los logs. Usar cuando el usuario pida "plan de la semana", "qué hago la próxima semana" o una revisión semanal.
---

1. Sincronizar: `git fetch origin main && git checkout main && git pull origin main`.
2. Semana objetivo: por defecto la siguiente semana ISO en Lima
   (`TZ=America/Lima date -d 'next monday' '+%G-W%V'`).
3. Leer `perfil.md`, `rutina/semana.md`, `rutina/grupos/`, el plan de la semana anterior si existe, y los logs de
   las últimas 2–4 semanas.
4. Resumen de la semana que termina: sesiones hechas vs. planificadas, progresos, estancamientos,
   molestias reportadas.
5. Aplicar las reglas de progresión de CLAUDE.md ejercicio por ejercicio. Cada cambio de carga
   con su motivo en una línea ("subo a 62.5 kg: completaste 3x12 dos veces").
6. Escribir `planes/AAAA-Www.md` con la misma estructura de días que `rutina/semana.md`
   (sábado con Bloque A y B), cargas concretas, y arriba el resumen y los cambios clave.
7. Si detecta que la rutina misma debería cambiar (estancamiento largo, molestia recurrente),
   sugerirlo pero NO cambiar `rutina/grupos/` sin confirmación del usuario.
8. `git add planes && git commit -m "plan: AAAA-Www" && git push origin main`.
