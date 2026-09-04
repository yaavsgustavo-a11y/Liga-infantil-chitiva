# AUDITORIA_CRUZADA.md — Revisión de consistencia entre documentos

> Versión 1.0 · 04/09/2026 · Responsable: Coordinación de Marketing y Comercial.
> Objetivo: detectar y resolver contradicciones entre Estrategia, Comercial, Marketing, Diseño, Producción Audiovisual, Captación, Cronograma, Responsabilidades y la información dependiente de otras áreas (Finanzas, Operación, Deportivo, Reglamento, Tecnología).

## 1. Método

Se revisaron los 17 documentos + solicitudes + ejecutivo contrastando: cifras, fechas, precios, promesas comunicables, responsables (RACI) y dependencias. Se buscaron: (a) datos comunicados como confirmados que en realidad están POR VALIDAR; (b) cifras/fechas inconsistentes entre documentos; (c) responsabilidades técnicas mal asignadas a MKT/COM/DIS/AV; (d) promesas condicionadas usadas sin condición.

## 2. Matriz de consistencia de datos clave

| Dato | Valor único usado en todo el repo | Estado |
|---|---|---|
| N.º de colegios meta | 7 | CONFIRMADO |
| Categorías | 1.º-2.º / 3.º-4.º / 5.º-6.º (3) | CONFIRMADO |
| Jugadores por equipo (ref.) | ~15 | POR VALIDAR (Deportivo) |
| Participantes estimados | ≤ 315 (7×3×15) | POR VALIDAR (estimación) |
| Ventana de temporada | Oct–Dic 2026 (J1 05 Oct → Final 14–18 Dic) | PROPUESTA (Deportivo/Operación) |
| Ventana de visitas a colegios | 07–25 Sep 2026 | CONFIRMADO (doc interno) |
| Instalaciones | 2 F7, 1 F5, 1 pádel | CONFIRMADO |
| Modelo de participación | Híbrido (C) recomendado | PROPUESTA (Dirección decide) |
| Precio | — | POR VALIDAR (Finanzas) |
| Modalidad | Mixta (hipótesis) | POR VALIDAR (Deportivo) |
| Funcionalidades plataforma | No comunicadas hasta confirmar | POR VALIDAR (Tecnología) |

**Resultado:** las cifras y fechas se usan de forma **idéntica** en todos los documentos (se centralizaron en `common.py`). No se detectaron discrepancias numéricas.

## 3. Hallazgos y resoluciones

| # | Hallazgo potencial | Documentos | Resolución aplicada |
|---|---|---|---|
| A-01 | Riesgo de comunicar "sigue tu puntaje / revive tus jugadas" como confirmado | Doc 04, 06 | Marcado explícitamente POR VALIDAR (TE-01/02); Doc 06 §9.3 lo prohíbe hasta autorización. Coherente. |
| A-02 | Precio aparece en varios docs | Doc 02, 04, 05, 10 | En todos se marca POR VALIDAR (Finanzas); ningún doc fija cifra. Coherente. |
| A-03 | Modelo de participación recomendado | Doc 01, 02, 05, 09 | Todos recomiendan híbrido (C) y remiten la decisión a Dirección/Finanzas (DR-04). Coherente. |
| A-04 | Calendario de jornadas | Doc 04, 12, CRONOGRAMA.md | Mismo calendario (J1 05 Oct…), siempre marcado PROPUESTA/POR VALIDAR. Coherente. |
| A-05 | Uso de imagen de menores | Doc 05, 06, 08, 09, 14 | Todos condicionan a consentimiento legal (LG-03/AV-01). Coherente. |
| A-06 | Responsabilidades técnicas a MKT/DIS/AV | Doc 13 (RACI) | Verificado: categorías, formato, precio, seguridad, reglamento y tecnología tienen R en DEP/FIN/OPE/LEG/TEC; MKT/DIS/AV son C/I. Coherente. |
| A-07 | Metas de KPIs | Doc 01, 05, 11, EXEC | Cifras alineadas (7 colegios, ≥60% prospectos, ≥30 alumnos, etc.) y marcadas POR VALIDAR. Coherente. |
| A-08 | Fechas límite de decisiones/pendientes | DECISIONES.md, PENDIENTES.md, Doc 15, SOL, EXEC | Fechas alineadas (críticas 09–18 Sep). Coherente. |
| A-09 | Ubicación de Doc 17 | README, repo | Se creó carpeta `17_mejora_continua/`; README actualizado. Resuelto. |
| A-10 | Nombre de la liga | Todos | Se usa placeholder "[NOMBRE LIGA]" / nombre largo actual, siempre sujeto a DR-02. Coherente (no se inventó un nombre como definitivo). |

## 4. Conclusión

No se detectaron **contradicciones sustantivas** entre documentos. Los puntos sensibles (precio, tecnología, modalidad, uso de imagen, calendario) se tratan de forma uniforme como POR VALIDAR con responsable y fecha. La versión del repositorio es **internamente coherente** y lista para validación de Dirección.

## 5. Recomendación de control

- Mantener `common.py` como fuente única de datos al regenerar documentos, para preservar la consistencia.
- Al cerrar cada validación (PENDIENTES.md), actualizar el dato en todos los documentos afectados y subir la versión (CONTROL_VERSIONES.md).
