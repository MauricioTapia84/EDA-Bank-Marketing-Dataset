# Mapa de Agentes — Bank Marketing Dataset

Este repositorio es un proyecto de datos enfocado en la preparación y análisis del dataset `Bank Marketing`, centrado en notebooks y documentación de soporte.

## Orquestador principal
| Agente | Rol | Función Principal |
|---|---|---|
| `@system-orchestrator` | Coordinación general | Punto de entrada único para todas las solicitudes; decide si derivar a estudio, datos o notebooks. |

## Orquestadores de dominio
| Agente | Dominio | Uso principal |
|---|---|---|
| `@study-orchestrator` | Documentación | Lee actas y documentos en `bank_marketing/docs/md-fuente/` y responde consultas metodológicas. |
| `@data-orchestrator` | Datos | Maneja EDA, limpieza, preprocesamiento y validación de transformaciones. |
| `@notebook-agent` | Notebooks | Edita y sugiere cambios para `.ipynb` manteniendo formato XML de celdas. |

## Reglas de uso
- Inicia siempre por `@system-orchestrator` para decidir el dominio.
- Usa `@study-orchestrator` para requerimientos de proyecto, actas y metas de entrega.
- Usa `@data-orchestrator` para tareas de pipeline, `ColumnTransformer`, selección de variables y validación de entrenamientos.
- Usa `@notebook-agent` cuando la tarea implique modificar celdas de notebooks.

## Componentes clave
- `bank_marketing/notebooks/01_preprocesamiento_proyecto.ipynb`
- `bank_marketing/notebooks/preprocessing.py`
- `bank_marketing/data/raw/bank-additional-full.csv`
- `bank_marketing/data/processed/`
- `bank_marketing/docs/md-fuente/`

