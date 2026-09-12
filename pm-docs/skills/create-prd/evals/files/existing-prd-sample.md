# Recordatorios de renovación de suscripción — PRD

| Campo | Valor |
| :---- | :---- |
| **Autor** | Marta Ruiz |
| **Estado** | En revisión |
| **Equipo** | Billing |
| **Fecha de creación** | 2026-08-01 |
| **Fecha de lanzamiento objetivo** | 2026-10-15 |
| **Stakeholders / reviewers** | Diego (Eng Lead), Sara (Design) |

> Documento vivo — se actualiza conforme se resuelven los issues abiertos y evoluciona el enfoque.

---

## BLOQUE I — Problem Alignment

### 1. El Problema

El 22% de los usuarios que cancelan su suscripción dicen en la encuesta de salida que "se olvidaron de que se iba a renovar". No hay ningún aviso antes del cobro automático.

**Qué NO estamos resolviendo**

* No vamos a rediseñar el flujo de cancelación en sí.
* No vamos a añadir opciones de pausa de suscripción en esta fase.

### 2. Enfoque de Alto Nivel

Enviar un recordatorio por email e in-app unos días antes de la renovación automática, con opción directa de cancelar o cambiar de plan desde el propio aviso.

### 3. Objetivos y Éxito

| Métrica | Objetivo | Por qué importa |
| :---- | :---- | :---- |
| % cancelaciones por "olvido" | Reducir del 22% al 10% | Directamente ligado al problema detectado |

---

## BLOQUE II — Solution Alignment

### 4. Features Clave

**Para esta fase**

* **Email de recordatorio** — se envía 5 días antes de la renovación.
* **Aviso in-app** — banner en el dashboard los últimos 3 días antes de la renovación.

**Diferido a una fase futura** (considerado, descartado por ahora)

* **Recordatorio por SMS** — se descarta por ahora por coste de integración con el proveedor de SMS.

### 5. Flujos Clave

#### Flujo: Email de recordatorio

1. El usuario recibe un email 5 días antes de la renovación con el importe y la fecha.
2. Puede pulsar "Gestionar mi plan" y llega directamente a la pantalla de suscripción.

### 6. Issues Abiertos y Decisiones Clave

| Pregunta / Decisión | Estado | Trade-offs considerados | Resolución |
| :---- | :---- | :---- | :---- |
| ¿Se envía el aviso también a cuentas en plan gratuito? | Abierto | Podría confundir a usuarios free sin fecha de renovación real | — |

---

## BLOQUE III — Launch Readiness

### 7. Hitos Clave

| Hito | Fecha | Audiencia | Qué se prueba/valida |
| :---- | :---- | :---- | :---- |
| Beta | 2026-09-20 | 5% de usuarios con renovación próxima | Que el email se envía a tiempo y el CTA funciona |
| Lanzamiento | 2026-10-15 | Todos los usuarios | Impacto en tasa de cancelación |

### 8. Launch Checklist

| Área | Pregunta a responder | Responsable | Estado |
| :---- | :---- | :---- | :---- |
| **Support** | ¿Qué necesita saber el equipo de soporte antes del lanzamiento? | [PENDIENTE: confirmar con Support] | Pendiente |
| **Growth & Data** | ¿Qué se necesita trackear? | Laura (Data) | OK |
| **Marketing** | ¿Hace falta comunicación externa? | [PENDIENTE: confirmar con Marketing] | Pendiente |
| **Enterprise** | ¿Afecta a clientes enterprise? | [PENDIENTE: confirmar con Enterprise] | Pendiente |
| **Platform** | ¿Hay dependencias de infraestructura? | [PENDIENTE: confirmar con Platform] | Pendiente |
| **Security & Privacy** | ¿Hay implicaciones de datos personales? | [PENDIENTE: confirmar con Security & Privacy] | Pendiente |
