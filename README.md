# ETL Seguros Pipeline

## Descripción
Este proyecto implementa un pipeline ETL para procesar datos de seguros.

## Tecnologías utilizadas
- Python
- Pandas
- PostgreSQL
- Render
- Google Colab
- GitHub

## Arquitectura del pipeline

CSV → GitHub → Python ETL → PostgreSQL → Consultas SQL

## Proceso ETL

### Extract
Los datos se obtienen desde archivos CSV almacenados en GitHub.

### Transform
Se realizan transformaciones como:
- limpieza de datos
- conversión de fechas
- conversión de columnas numéricas

### Load
Los datos transformados se cargan en PostgreSQL en la nube usando SQLAlchemy.

## Tablas cargadas
- clientes
- aseguradoras
- corredores
- tipos_seguro
- polizas
- siniestros
