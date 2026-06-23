# Project-NovaRetail# 

Explorando Factores de Comportamiento en NovaRetail+

Análisis exploratorio de datos (EDA) orientado a identificar relaciones estadísticas entre las variables de comportamiento de clientes en la plataforma de comercio electrónico **NovaRetail+**.

---

## 📋 Descripción del Proyecto

Este proyecto forma parte de un programa de formación en ciencia de datos. El objetivo principal es explorar y cuantificar las relaciones entre las distintas variables del dataset de clientes de NovaRetail+ para generar hallazgos accionables que apoyen la toma de decisiones del negocio.

El análisis no busca establecer relaciones de causalidad, sino identificar patrones de coocurrencia estadísticamente significativos que puedan orientar estrategias de retención, conversión y crecimiento.

---

## 📁 Dataset

**Archivo:** `novaretail_comportamiento_clientes_2024.csv`  
**Registros:** 15,000 clientes | **Variables:** 12 columnas | **Nulos:** ninguno

| Variable | Descripción |
|---|---|
| `id_cliente` | Identificador único del cliente |
| `edad` | Edad del cliente |
| `nivel_ingreso` | Ingreso anual estimado del cliente |
| `visitas_mes` | Visitas a la app o sitio web durante el mes |
| `compras_mes` | Número de compras realizadas en el mes |
| `gasto_publicidad_dirigida` | Gasto en anuncios asignado al usuario |
| `satisfaccion` | Calificación de satisfacción (escala 1–5) |
| `miembro_premium` | Suscripción premium: 1 = sí, 0 = no |
| `abandono` | Churn del cliente: 1 = abandonó, 0 = activo |
| `tipo_dispositivo` | Dispositivo utilizado (móvil / escritorio / tablet) |
| `region` | Región geográfica (norte / sur / oeste / este) |
| `ingreso_anual` | Ingreso anual generado por el cliente para la empresa ⭐ |

> **Métrica principal de análisis:** `ingreso_anual`

---

## 🔬 Metodología

El proyecto se estructura en 6 secciones:

1. **Carga y exploración del dataset** — inspección inicial, tipos de datos y estructura general.
2. **Preparación de datos y supuestos** — limpieza, corrección de tipos, exploración por tipo de variable y definición de supuestos metodológicos.
3. **Visualización de relaciones** — heatmap de correlaciones y matriz de dispersión (pairplot) para variables clave.
4. **Coeficientes de correlación** — análisis numérico con cuatro métricas estadísticas según el tipo de variable.
5. **Interpretación de resultados para el negocio** — traducción de hallazgos estadísticos a implicaciones accionables.
6. **Limitaciones y próximos pasos** — alcance del análisis y recomendaciones metodológicas futuras.

### Coeficientes utilizados

| Coeficiente | Uso |
|---|---|
| **Pearson** | Relaciones lineales entre variables numéricas |
| **Spearman** | Relaciones monótonas (validación de Pearson) |
| **Punto-biserial** | Relación entre variable numérica y binaria |
| **V de Cramér** | Asociación entre variables categóricas |

---

## 📊 Principales Hallazgos

| # | Variables | Coeficiente | Implicación |
|---|---|---|---|
| 1 | `compras_mes` ↔ `ingreso_anual` | Pearson **0.97** | Indicador operativo en tiempo real del valor del cliente |
| 2 | `visitas_mes` ↔ `ingreso_anual` | Pearson **0.34** | Las visitas no garantizan ingresos; priorizar conversión |
| 3 | `visitas_mes` ↔ `gasto_publicidad_dirigida` | Pearson **0.58** | La inversión publicitaria alcanza a los usuarios activos |
| 4 | `visitas_mes` ↔ `compras_mes` | Pearson **0.35** | Optimizar el embudo de conversión (CRO) |
| 5 | `miembro_premium` ↔ `ingreso_anual` | Biserial **0.093** | Perfiles de mayor ingreso tienen afinidad con premium |
| 6 | `miembro_premium` ↔ `satisfaccion` | Biserial **0.025** | Programa premium se asocia con mejor experiencia |
| 7 | `abandono` ↔ `satisfaccion` | Biserial **−0.024** | Satisfacción baja es señal temprana de churn |
| 8 | `region` ↔ `tipo_dispositivo` | V Cramér **0.012** | Sin asociación → infraestructura responsiva unificada |

---

## 🛠️ Tecnologías

- Python 3
- pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy (`pointbiserialr`, `chi2_contingency`)
- Jupyter Notebook

---

## 🚀 Cómo ejecutar el proyecto

1. Clona el repositorio:
   ```bash
   git clone https://github.com/tu-usuario/novaretail-eda.git
   cd novaretail-eda
   ```

2. Instala las dependencias:
   ```bash
   pip install pandas numpy matplotlib seaborn scipy jupyter
   ```

3. Coloca el archivo `novaretail_comportamiento_clientes_2024.csv` en la ruta `/datasets/` o ajusta la ruta en el notebook.

4. Abre el notebook:
   ```bash
   jupyter notebook S8_Student_Version-Project-NovaRetail.ipynb
   ```

---

## ⚠️ Limitaciones

- El análisis es **correlacional**, no causal. Los coeficientes miden coocurrencia, no causalidad.
- El dataset representa un **corte temporal de un solo mes**, lo que limita el análisis de tendencias y estacionalidad.
- No se incluyen variables cualitativas de contexto (soporte, encuestas abiertas) que podrían explicar el abandono con mayor profundidad.

---

## 🔭 Próximos Pasos

- Implementar un **sistema de alertas transaccionales** basado en la correlación compras–ingresos.
- Desarrollar mejoras de **UX/UI** para optimizar la conversión dentro de la plataforma.
- Evolucionar hacia un **análisis longitudinal y de cohortes** con datos históricos de al menos 3 años.
- Diseñar un **Early Warning System** para usuarios con baja satisfacción en riesgo de abandono.

---

## 👤 Autor

Proyecto desarrollado como parte de un programa de bootcamp en ciencia de datos.
