# Problema de Reglas de Asociación

## 📊 Descripción del Proyecto

Análisis de reglas de asociación sobre el dataset **Online Retail II** para identificar productos que tienden a comprarse de forma conjunta y diseñar paquetes promocionales.

### Dataset: DATASET_RP_3
- **Origen:** Online Retail II (tienda online Reino Unido)
- **Período analizado:** 2010 - 2011
- **Tipo de datos:** Transacciones de venta
- **Clientes principales:** Mayoristas y minoristas
- **Productos:** Incluye regalos y souvenirs

---

## 🎯 Objetivos

✅ Explorar los ítems del catálogo  
✅ Extraer el tamaño de cada transacción  
✅ Descartar compras canceladas (id_compra que comienzan con 'C')  
✅ Identificar reglas de asociación significativas  
✅ Optimizar el valor mínimo de soporte para obtener reglas relevantes  
✅ Diseñar paquetes promocionales basados en patrones de compra conjunta  

---

## 📋 Variables del Dataset

| Variable | Descripción |
|----------|-------------|
| `id_compra` | Número de factura (si empieza con 'C' = compra cancelada) |
| `item` | Descripción o nombre del producto |

---

## 📁 Estructura del Proyecto

```
.
├── README.md                    # Este archivo
├── .gitignore                   # Archivos a ignorar en Git
├── Problema_Reglas_Asociacion.Rproj  # Proyecto de R Studio
├── data/                        # Datos
│   └── DATASET_RP_3.csv        # Dataset original (descargado externamente)
├── scripts/                     # Scripts de análisis
│   ├── 01_carga_exploracion.R   # Lectura y exploración de datos
│   ├── 02_limpieza_datos.R      # Limpieza y preprocesamiento
│   ├── 03_analisis_transacciones.R  # Análisis de transacciones
│   └── 04_reglas_asociacion.R   # Minería de reglas de asociación
├── resultados/                  # Salidas del análisis
│   ├── graficos/               # Visualizaciones
│   └── reportes/               # Reportes y tablas
└── informe/                     # Documentación final
    └── INFORME_REGLAS_ASOCIACION.Rmd  # Informe en formato R Markdown
```

---

## 🚀 Cómo usar este proyecto

### Requisitos previos
- R versión 4.0 o superior
- R Studio
- Paquetes necesarios: `tidyverse`, `arules`, `arulesViz`, `readxl`

### Instalación de dependencias

```r
# Instalar paquetes necesarios
packages <- c("tidyverse", "arules", "arulesViz", "readxl", "knitr", "rmarkdown")
install.packages(packages)
```

### Ejecución del análisis

1. **Abrir el proyecto** en R Studio
2. **Ejecutar los scripts en orden:**
   ```r
   source("scripts/01_carga_exploracion.R")
   source("scripts/02_limpieza_datos.R")
   source("scripts/03_analisis_transacciones.R")
   source("scripts/04_reglas_asociacion.R")
   ```

3. **Generar informe:**
   ```r
   rmarkdown::render("informe/INFORME_REGLAS_ASOCIACION.Rmd")
   ```

---

## 📊 Etapas del Análisis

### 1️⃣ Carga y Exploración
- Leer el dataset CSV
- Examinar estructura y variables
- Identificar valores faltantes y anomalías
- Explorar el catálogo de ítems

### 2️⃣ Limpieza de Datos
- **Descartar compras canceladas** (id_compra con prefijo 'C')
- Eliminar registros con datos incompletos
- Validar integridad de datos
- Verificar rangos de valores

### 3️⃣ Análisis de Transacciones
- Agrupar productos por compra
- Calcular el tamaño de cada transacción
- Estadísticas descriptivas por transacción
- Visualizar distribución de tamaños

### 4️⃣ Reglas de Asociación
- Aplicar algoritmo **Apriori**
- Ajustar parámetros:
  - **Soporte mínimo:** para reducir cantidad de reglas
  - **Confianza mínima:** 0.5 - 0.7 (típico)
  - **Lift mínimo:** >1 (asociación positiva)
- Extraer y clasificar reglas
- Interpretar resultados

---

## 📌 Consideraciones Importantes

⚠️ **Descartar compras anuladas:** No incluir en el análisis compras cuyo id_compra comienza con 'C'

⚠️ **Validación de soporte:** Experimentar con valores de soporte mínimo para obtener un número manejable de reglas significativas

⚠️ **Interpretación:** Las reglas deben ser comercialmente viables para diseñar paquetes promocionales

---

## 📝 Entrega

- **Fecha inicio:** 15/06/2026 - 08:00
- **Fecha fin:** 11/07/2026 - 23:59
- **Entregables:**
  - Scripts R documentados
  - Informe con análisis y conclusiones
  - Tablas de reglas de asociación
  - Visualizaciones

---

## 📚 Referencias

- [Algoritmo Apriori](https://en.wikipedia.org/wiki/Apriori_algorithm)
- [Paquete arules en R](https://cran.r-project.org/web/packages/arules/)
- [Market Basket Analysis](https://en.wikipedia.org/wiki/Affinity_analysis)

---

**Autor:** Bertha46  
**Última actualización:** Julio 2026
