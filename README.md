# ETL Seguros Pipeline

## Descripción

Este proyecto implementa un pipeline ETL (Extract, Transform, Load) utilizando un dataset de seguros.

El proceso consiste en:

* extraer datos desde archivos CSV en GitHub
* limpiar y transformar los datos con Python (Google Colab)
* separar registros válidos y rechazados
* almacenar resultados en archivos curated y rejects

---

## 🛠️ Tecnologías utilizadas

* Python
* Pandas
* Google Colab
* GitHub
* PostgreSQL (Render Cloud)

---

## Arquitectura del pipeline

```
CSV (GitHub)
     ↓
Google Colab (ETL por dataset)
     ↓
Transformación y limpieza
     ↓
Separación de datos (validos / rechazados)
     ↓
Archivos curated / rejects
     ↓
PostgreSQL Cloud
     ↓
Consultas SQL
```

---

## Estructura del proyecto

```
etl-seguros-pipeline
│
├── data
│   ├── raw
│   ├── curated
│   └── rejects
│
├── notebooks
│   ├── etl_clientes.ipynb
│   ├── etl_aseguradoras.ipynb
│   ├── etl_corredores.ipynb
│   ├── etl_tipos_seguro.ipynb
│   ├── etl_polizas.ipynb
│   └── etl_siniestros.ipynb
│
└── README.md
```

---

## Proceso ETL

### Extract

Los datos se obtienen desde archivos CSV almacenados en GitHub en la carpeta:

```
data/raw
```

---

### Transform

Se aplican procesos de limpieza y transformación como:

* normalización de nombres de columnas
* eliminación de espacios
* conversión de datos vacíos a valores nulos
* eliminación de duplicados
* conversión de fechas
* conversión de valores numéricos

---

### Validación de datos

Se separan los datos en:

* **datos válidos (curated)** → cumplen reglas de calidad
* **datos rechazados (rejects)** → contienen errores

Ejemplos de errores:

* campos obligatorios vacíos
* fechas inválidas
* valores numéricos incorrectos

---

### Load

Los datos procesados se almacenan en:

```
data/curated
data/rejects
```

y posteriormente se cargan a PostgreSQL en la nube.

---

## 📊 Datasets procesados

* clientes
* aseguradoras
* corredores
* tipos_seguro
* polizas
* siniestros

Cada dataset tiene su propio notebook ETL.

---

## Consultas de análisis

Ejemplos de consultas realizadas en PostgreSQL:

```sql
SELECT COUNT(*) FROM clientes;
```

```sql
SELECT COUNT(*) FROM polizas;
```

```sql
SELECT estado, COUNT(*)
FROM siniestros
GROUP BY estado;
```

```sql
SELECT SUM(monto_asegurado)
FROM polizas;
```

---

## Resultado

Se construyó un pipeline ETL completo que permite:

* procesar datos desde archivos CSV
* limpiar y validar información
* organizar datos en estructuras profesionales
* cargar datos en una base de datos en la nube
* realizar análisis mediante consultas SQL

---

##  


