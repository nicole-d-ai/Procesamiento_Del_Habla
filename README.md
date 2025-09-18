# 📖 Procesamiento del Habla con Python

Este proyecto utiliza **Python** para descargar, limpiar y procesar el texto del poema *El Gaucho Martín Fierro* desde un archivo PDF.   El objetivo es **extraer estrofas organizadas**, filtrando números romanos, pies de página y líneas vacías, y almacenarlas en una lista de diccionarios.

## ⚙️ Tecnologías utilizadas
- [Python 3](https://www.python.org/)
- [requests](https://docs.python-requests.org/) → para descargar el PDF desde la web.
- [pdfplumber](https://github.com/jsvine/pdfplumber) → para leer y extraer texto de los PDF.
- [regex](https://pypi.org/project/regex/) → para detectar pies de página y números romanos.

---

## 📂 Estructura del proyecto
- **Descarga del PDF** → se trae el archivo desde una URL y se guarda localmente en modo binario.
- **Limpieza del texto** → se eliminan caracteres raros y espacios innecesarios.
- **Procesamiento** → se recorren línea por línea:
  - Se ignoran líneas vacías y pies de página.
  - Se identifican números romanos como cabeceras.
  - Se cuentan los versos y se agrupan en estrofas de 6 líneas.
  - Si al final de una página queda un resto, se guarda igual.
- **Salida final** → una lista de diccionarios con:
  - `nro_pag` → número de página.
  - `cant_versos` → cantidad de versos en la estrofa.
  - `texto` → contenido completo de la estrofa.
