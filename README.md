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

## 6) Visualización

- Dashboard: link (Power BI/Looker/Tableau)
- Video: GIF/YouTube corto (<90s)
- App: Streamlit/HF Space (si aplica)

/data /notebooks /sql /app /reports ...


**`.gitignore` mínimo (Python/datos):**

## Generalidades
Python

pycache/
*.pyc
.venv/

Jupyter checkpoints

.ipynb_checkpoints/

Credenciales

.env

Datos pesados/privados

data/raw/*
data/private/*
*.pbix
*.csv

## 7) > Tip: para archivos pesados usa **Git LFS** o súbelos a Drive/S3 y provee un script de descarga.

## 8) Crea tu **primer proyecto** a partir de la plantilla
Opción A (en GitHub): “Use this template” → nombre: `proyecto-paid-media-roas` → Create.  
Opción B (local):
```bash
git clone git@github.com:usuario/template-datos-bi.git proyecto-paid-media-roas
cd proyecto-paid-media-roas
rm -rf .git
git init
git remote add origin git@github.com:usuario/proyecto-paid-media-roas.git
git add .
git commit -m "init: estructura plantilla"
git push -u origin main


## 9) Crea rama de trabajo
git checkout -b feat/etl-facebook-api
# cambios...
git add .
git commit -m "feat(etl): agrega extracción API Meta y normalización"
git push -u origin feat/etl-facebook-api

## 10)
Luego en GitHub → Pull Request → revisas y haces Merge a main.

## 11) Issues y Project Board (Kanban simple)

En tu repo: Issues = tareas (“Crear script de descarga”, “Diseñar dashboard”).

Projects → crea un tablero “To do / In progress / Done”.

Asocia cada Issue a una columna. Esto ayuda mucho si estás armando 3–4 proyectos a la vez.

## 12) README del perfil fijando 3–5 repos

Perfil → “Customize your pins” → pin proyecto-paid-media-roas, proyecto-cdg-retail, proyecto-scoring-cobranza, etc.

## 13)
name: Link Checker
on: [push, pull_request]
jobs:
  linkchecker:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Check Markdown Links
        uses: lycheeverse/lychee-action@v1
        with:
          args: --verbose --no-progress .

