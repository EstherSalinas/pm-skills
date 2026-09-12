PRD — Filtros guardados en el listado de tickets (v2)

Autor: Carlos M.
Última edición: 12 de marzo de 2026
Estado: pendiente de revisión con ingeniería

## Resumen

El equipo de soporte pierde tiempo reconstruyendo los mismos filtros una y otra vez en el
listado de tickets. Queremos que puedan guardar combinaciones de filtros y reutilizarlas.

## Contexto y justificación

Hoy el listado de tickets permite filtrar por estado, prioridad, cola, agente asignado y
etiqueta, pero la configuración se pierde al recargar o al cambiar de vista. Según el estudio
de tiempos que hicimos en enero con 8 agentes, un agente aplica de media 14 filtros al día y
tarda unos 40 segundos en reconstruir cada configuración habitual. El objetivo es bajar eso a
menos de 10 segundos por configuración.

Además, los agentes senior nos han dicho en las 1:1 que la falta de filtros guardados es una de
las razones por las que acaban trabajando con hojas de cálculo paralelas, lo que nos deja sin
visibilidad de cómo priorizan realmente.

## Requisitos

1. El usuario puede guardar la combinación de filtros activa dándole un nombre.
2. Los filtros guardados aparecen en un desplegable en la parte superior del listado.
3. El usuario puede renombrar y eliminar sus filtros guardados.
4. Al seleccionar un filtro guardado, el listado se actualiza sin recargar la página.
5. El último filtro usado se recuerda al volver a entrar en el listado.
6. Los filtros guardados respetan los permisos de cola del agente (no puede guardar un filtro
   que muestre colas a las que no tiene acceso).
7. Si hay tiempo: poder compartir un filtro guardado con el resto del equipo.

## Notas técnicas

Se guardará como JSON en la tabla de preferencias de usuario que ya existe. No hace falta
migración. Diego estima 5-8 días de trabajo de frontend y 2 de backend.

## Dudas

- ¿Los filtros guardados son por usuario o se pueden definir a nivel de equipo? Pendiente
  hablar con Diego y con la responsable de soporte.
- ¿Hay límite de filtros guardados por usuario?
