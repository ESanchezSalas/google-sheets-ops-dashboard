# Dashboard operativo – Google Sheets (M1)

**Stack:** Google Sheets (ETL ligera + Tablas dinámicas + Charts) · Excel (fuente)  
**Dataset:** Master Global Super Store (2013–2014)

## 🎯 Objetivo
Construir un **dashboard operativo** que permita entender ventas, costos y rentabilidad por **categoría, subcategoría, mercado, región**, además de **métodos de envío y prioridad de pedido**.

## 📦 Fuente de datos
- `data/raw/MasterGlobalSuperStore.xlsx` (archivo original)
- Presentación ejecutiva: `docs/presentacion/masterglobalsuperstore.pdf`

## 🔧 Proceso (ETL liviana en Sheets)
1) Importar el Excel a Google Sheets.  
2) **Limpieza y normalización** (quitar filas/columnas irrelevantes, acotar periodo 2013–2014).  
3) Generar **clave primaria** combinando `Order_ID` + `Product_ID`.  
4) Calcular **Lead time de entrega** (`Ship_Date - Order_Date`) y variables cuantitativas auxiliares.  
5) Tablas dinámicas y gráficos para KPIs de negocio.  

## 📊 Hallazgos clave
- **Ventas por categoría:** *Office Supplies* concentra ~46 % del total.  
- **Subcategorías top:** Chairs, Bookcases, Binders y Storage (> $35M cada una).  
- **Mercados:** *LATAM* lidera (~$187M), seguido por *APAC* y *North America*.  
- **Regiones:** destacan *Central* y *North*; *Canada* es la menor.  
- **Ventas y costos por año:** ventas crecen ~24 % (2013→2014) y suben costos; 2014 es el año más rentable.  
- **Envíos:** *Standard Class* concentra ~60 % de envíos y también la mayor cifra de ventas (~$240M).  
- **Prioridad de pedido:** predominan *Medium* (~50 %) y *High* (~33 %).  
Estas conclusiones provienen del análisis detallado del dataset y la presentación adjunta.  [oai_citation:0‡masterglobalsuperstore.pdf](file-service://file-DLYJ1k7ZXBoZjiZ3AfGdno)

## 🖥️ Dashboard (vista)

![KPIs – vista general](img/masterglobalsuperstore1.jpeg)
![Detalle por categoría / región](img/masterglobalsuperstore2.jpeg)

## 🗂️ Estructura del repo
├── README.md
├── data
│   └── raw
│       ├── MasterGlobalSuperStore.xlsx
│       └── README.md
├── docs
│   ├── README.md
│   └── presentacion
│       ├── masterglobalsuperstore.pdf
│       └── README.md
└── img
├── kpis.png
├── categorias.png
└── README.md

## 🚀 Cómo reproducir (rápido)
1) Abre `MasterGlobalSuperStore.xlsx` en Google Sheets.  
2) Replica los pasos de “Proceso (ETL liviana)” y genera tablas dinámicas por:
   - Categoría / Subcategoría  
   - Mercado / Región  
   - Año (Ventas/Costos)  
   - Ship Mode (envíos y ventas)  
   - Order Priority  
3) Crea charts ejecutivos (barras apiladas, líneas, treemap o doughnut según el caso).
4) Monta una página de “Resumen” con KPIs principales y navegación.

## 🗓️ Próximos pasos
- Agregar segmentaciones (slicers) por año/mercado.  
- Exportar snapshots mensuales a `img/`.  
- Publicar el dashboard y enlazarlo aquí.

---
**Autor:** Eric Sanchez · Data Analyst (Admin & Finance)
