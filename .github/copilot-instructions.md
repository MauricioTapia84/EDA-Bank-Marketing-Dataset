# Reglas de Operación — Bank Marketing Dataset

## 🧭 Contexto del repositorio
Este repositorio es un proyecto de análisis y preprocesamiento de datos para el dataset `Bank Marketing`. El trabajo principal está en el directorio `bank_marketing/`, con notebooks, scripts de limpieza y documentación de soporte.

## 🧯 Directrices para el agente
1. Responde en español cuando el usuario escribe en español.
2. Prioriza `bank_marketing/notebooks/` y `bank_marketing/docs/md-fuente/` para entender el flujo del proyecto.
3. No asumas que este repositorio contiene un backend Node/React o un pipeline empresarial: este es un proyecto de datos y notebooks.
4. Cuando modifiques `.ipynb`, sugiere cambios en celdas específicas y evita reescribir grandes bloques sin necesidad.
5. Mantén la trazabilidad de los datos: no mezcles `X_train` y `X_test`, y no uses estadísticas del conjunto completo para entrenar transformaciones.
6. Si se necesitan datos procesados, usa `bank_marketing/data/processed/` y genera los archivos desde `bank_marketing/data/raw/bank-additional-full.csv`.
7. Si una ruta de archivo es incorrecta o falta un archivo, explica claramente qué debe generarse y desde dónde.

---

## 🎓 Sistema de Estudio y Documentación del Proyecto

### Agente de entrada global: @system-orchestrator
Para cualquier solicitud general en el repositorio, usar este orden de delegación:
1. @system-orchestrator clasifica la solicitud (PUNTO DE ENTRADA ÚNICO)
2. @study-orchestrator atiende material, dudas sobre el proyecto, requerimientos y documentación
3. @data-orchestrator atiende análisis de datos, reportes de negocio y métricas de barbería
4. @programming-orchestrator atiende desarrollo de software: APIs (Node.js), BD (Azure SQL), Frontend (React), tests, docs y arquitectura

### Agente de entrada: @study-orchestrator
Para cualquier solicitud relacionada con la comprensión del proyecto:
1. @study-orchestrator identifica la necesidad y delega
2. @content-reader lee el knowledge base en knowledge/ (donde reside el Acta de Constitución, Planes de Riesgo, etc.)
3. Genera resúmenes técnicos o responde dudas sobre los requerimientos del cliente

### Protocolo para solicitudes de conocimiento
Cuando el usuario pida resumir requerimientos, explicar planes o consultar la arquitectura:
1. Verificar si knowledge/ existe (generado a partir de Documentación/Documentos/)
2. Buscar el tema en knowledge/INDEX.md
3. Leer el archivo correspondiente y responder con precisión quirúrgica

### Inicializar el Knowledge Base de FadeBooker
\`\`\`bash
# Ubicación: Producto/back-fadebooker/
pip install -r scripts/requirements_extraction.txt
python scripts/extract_course_content.py --source "../../Documentación/Documentos" --output "../../knowledge"
\`\`\`

---

## 🔬 Reglas de Operación — Desarrollo y Calidad (FadeBooker)

## 🧬 Contexto y Referencia
Este proyecto sigue una arquitectura **Hexagonal (Clean Architecture)** en el backend y **Feature-Based Architecture** en el frontend. Todo desarrollo debe alinearse con estos patrones.

## 🤖 Roles de Agente
Consulta [.github/AGENTS.md](.github/AGENTS.md) para identificar qué agente debe realizar cada tarea.

### Jerarquía Operativa
- @system-orchestrator decide el subsistema.
- @programming-orchestrator coordina el desarrollo de software (Backend, Frontend, DB).
- @data-orchestrator coordina el análisis de métricas y reportes.
- @study-orchestrator facilita la navegación por la documentación técnica y administrativa.

### Estructura de Custom Agents
 - Agente de ciencia de datos: .github/agents/data/data-science.agent.md

## 🧭 Jerarquía de Instrucciones
1. Perfiles especializados en .github/agents/.
2. Mapa de roles en .github/AGENTS.md.
3. Estas reglas globales en .github/copilot-instructions.md.

## 📁 Estructura del Código
- **Backend**: Producto/back-fadebooker/src/ (Domain, Application, Infrastructure, Interfaces).
- **Frontend**: Producto/front-fadebooker/src/ (features, components, hooks, services).
- **Documentación**: Documentación/ y knowledge/.

## 🧩 Proyecto — Convenciones clave
- Inicia cualquier cambio de código con el contexto del backend en `Producto/back-fadebooker/` y el frontend en `Producto/front-fadebooker/`.
- El `knowledge/` es la fuente de requerimientos y criterios de negocio; `Documentación/md-fuente/` es la fuente de la API/documentación técnica.
- Usa `@system-orchestrator` como puerta de entrada en todas las solicitudes. Si el entorno lo permite, arranca desde `.github/prompts/route-through-system-orchestrator.prompt.md`.
- Mantén la arquitectura hexagonal en el backend y la organización feature-based en el frontend.
- Revisa `Documentación/md-fuente/INDICE_ENDPOINTS.md` antes de actualizar o documentar endpoints.

## 🧪 Repositorio de datos
Este proyecto no contiene un backend Node/React ni integraciones de producción. Concéntrate en los notebooks y la preparación de datos en `bank_marketing/`.

## 🛠 Stack relevante
- Python y Jupyter Notebooks para análisis y preprocesamiento.
- `pandas`, `scikit-learn`, `matplotlib`, `seaborn` y similares en notebooks.
- Documentación de soporte en `bank_marketing/docs/md-fuente/`.

## ✅ Validación recomendada
- Revisa el notebook ejecutando las celdas después de los cambios.
- Asegura que las rutas relativas en los notebooks sean coherentes con su ubicación en `bank_marketing/notebooks/`.
- Confirma que los resultados transformados mantengan consistencia de filas y que no se produzcan fugas de datos.

## 💡 Nota de proyecto
Si ves referencias a FadeBooker, Azure SQL, Mercado Pago o_FRONTEND_ en las instrucciones, ignóralas: este repositorio es un ejercicio de preparación de datos para el dataset `Bank Marketing`.
