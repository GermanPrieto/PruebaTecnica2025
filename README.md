# Prueba Técnica 2025 - RPA con PIX

Este proyecto implementa un flujo de automatización en **PIX Studio** que realiza las siguientes tareas:

1. **Consumo de API y Procesamiento de datos en base de datos**  
   - Se conecta a la API de productos `https://fakestoreapi.com/products`.  
   - Almacena los resultados en un archivo JSON (`\Data\Output\Productos.json`).  
   - Copia de JSON a OneDrive local (`OneDrive\RPA\Logs\Productos.json`). 
   - Parseo de JSON. 
   - Se guarda en una base de datos SQLite (`\BD\Productos.db`).  
   - Inserción de productos evitando duplicados.  

2. **Generación de Excel**  
   - Se genera un reporte en Excel (`\Data\Output\Reportes\Reporte_YYYY-MM-DD.xlsx`) con:  
     - **Hoja Productos**: 
        -  Todos los productos y sus datos.  
     - **Hoja Resumen**:  
       - Total de productos.  
       - Precio promedio general.  
       - Precio promedio por categoría.  
       - Cantidad de productos por categoría.  
   - Copia de Excel a OneDrive local (`OneDrive\RPA\Reportes\Reporte_YYYY-MM-DD.xlsx`). 

3. **Automatización Web - Formulario**  
   - Se abre un formulario de Google Forms.  
   - Se llenan automáticamente los campos (nombre, fecha y otros datos).  
   - Se carga el archivo Excel.  
   - Capturar una evidencia visual de la confirmación (`\Data\Output\Evidencias\formulario_confirmacion.png`).  

---

## 🚀 Requisitos
- PIX Studio instalado.  
- Conexión a Internet.  
- Tener instalada la extensión de Chrome para PIX.  
- SQLite ODBC Driver.  
- Sincronización local con **OneDrive** (el robot guarda los archivos directamente en la carpeta de OneDrive en el equipo).    

---

## ⚙️ Ejecución
1. Abrir el archivo del proyecto en PIX Studio.  
2. Configurar las variables necesarias (`ApiURL`, `DBConnection`, `FormURL`, etc.).  
3. Ejecutar el flujo principal `Main.pix`.  
4. Revisar los archivos generados en las carpetas `Output`y `BD`.  

---

## 📂 Estructura del proyecto

PruebaTecnica2025/
├── BD/
│ └── Productos.db
├── Data/
│ ├── Input/
│ ├── Outputs/
│ │ ├── Evidencias/
│ │ │ └── Productos_YYYY-MM-DD.json
│ │ ├── Reportes/
│ │   └── Reporte_YYYY-MM-DD.xlsx
│ ├── Temp/
│ └── Productos.json
├── Exceptions_Screenshots/
├── Framework/
│ ├── CloseApplications.pix
│ ├── KillApplications.pix
│ ├── ReadConfig.pix
│ ├── TakeScreenshot.pix
│ └── ValidateFolders.pix
├── APIDataToDB.pix
├── FillExcelData.pix
├── FillForm.pix
├── Main.pix
├── PruebaTecnica2025.pixproj
└── README.md

---
## 🔗 Enlace del formulario usado
[Formulario de Google Forms - Reporte de roductos](https://docs.google.com/forms/d/e/1FAIpQLSfLmRY7U6V4D2CHeHw4OULRuzt2Ysk3wfpWZKOxunN2zlDwNg/viewform?usp=header)

---
## Autor
German Andres Prieto Cardenas  
Agosto 2025