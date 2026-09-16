# Procesos de documentación · Ctrl.S

Los protocolos y flujogramas del servicio de **Documentación Quirúrgica**: cómo se organiza el
trabajo en ocho lotes, qué tareas tiene cada uno y cómo se modela cada disciplina.

Es la **fuente** del sistema de medición. Los tableros y la matriz que lo implementan viven en el
repo `ctrls-tableros`.

## Qué hay acá

| Archivo | Qué es |
|---|---|
| `lista-tareas.html` | **La lista de tareas maestra L1–L8.** Cada tarea con su tipo, disciplina, alcance y el estado que dispara en la matriz |
| `protocolos-modelado.html` · `.pdf` | Protocolos de modelado por disciplina — el paso a paso operativo |
| `hub-protocolos.html` | Índice de los protocolos |
| `flujogramas-lotes.html` · `.pdf` | Los ocho flujogramas juntos |
| `flujograma-general.html` | El flujo completo de punta a punta |
| `flujograma-L1-zoom.html` … `L8` | Un flujograma por lote, en detalle |
| `matriz-vista-completa.html` | Vista de referencia de la matriz de modelado |
| `modelo-mental.html` | El marco conceptual del sistema |
| `HANDOFF-lotes-matriz.md.pdf` | Handoff de la reforma de lotes y la matriz |

## Los ocho lotes y su peso

| Lote | | Peso |
|---|---|---|
| L1 | Modelo base | 5 |
| L2 | Detallado ARQ + parámetros | 5 |
| L3 | Ingenierías 2D | 10 |
| L4 | Ingenierías 3D | 10 |
| **L5** | **Coordinación + completitud** | **40** |
| L6 | Documentación | 10 |
| L7 | Locales | 10 |
| L8 | Detalles | 10 |

## Relación con los otros repos

- **`ctrls-tableros`** — la matriz de modelado, los tableros de avance y el criterio de medición.
  Implementa lo que este repo define.

---

*Ctrl.S Arquitectura*
