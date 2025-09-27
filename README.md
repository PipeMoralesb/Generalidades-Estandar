# Generalidades-Estandar
Bases de proyectos

# Título del Proyecto (Problema → Solución → Impacto)
**Rol:** (Autor) • **Fecha:** (mes/año) • **Stack:** SQL, Python, Power BI

## 1) Problema de negocio
Contexto breve (banca/retail/marketing). Qué se buscaba optimizar (p.ej., ROAS, mora, tiempo de reporte).

## 2) Datos
Fuente(s), tamaño, periodo, link o script de descarga (`data/get_data.py`), notas de calidad/ética.

## 3) Metodología
ETL (SQL/Python), features, modelo/medidas, visualizaciones, supuestos.

## 4) Resultados
- KPI1 (e.g., ↓ tiempo de reporte 40%)
- KPI2 (e.g., ↑ precisión de forecast 15%)
- KPI3 (e.g., +12% ROAS)

## 5) Cómo replicar
```bash
git clone <repo>
cd <repo>
python -m venv .venv && source .venv/bin/activate  # win: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab  # o streamlit run app/app.py
