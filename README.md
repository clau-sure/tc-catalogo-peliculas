# Catálogo de películas

**Team Challenge · Equipo 5**

En este reto hemos trabajado con los datos de MovieLens. Primero limpiamos y analizamos el catálogo con Pandas. Después usamos TMDB para buscar la sinopsis y la web oficial de diez películas, y Gemini para generar sinopsis en español.

## Equipo

- **Claudia Álvarez** · Repositorio, limpieza y análisis de datos (notebooks 01 y 02).
- **Jaime Revello** · TMDB y Gemini (notebooks 03 y 04).

## Cómo arrancar

```bash
git clone https://github.com/clau-sure/tc-catalogo-peliculas.git
cd tc-catalogo-peliculas
python -m venv .venv
```

Activa el entorno con `source .venv/bin/activate` en macOS o Linux, o con `.\.venv\Scripts\Activate.ps1` en PowerShell. Luego instala las dependencias con `python -m pip install -r requirements.txt`.

Puedes ejecutar los notebooks 01 y 02 con los CSV del repo. Para el 03 y el 04, copia `.env.example` como `.env` y rellena las claves:

- **TMDB (03)** · `TMDB_READ_ACCESS_TOKEN`. Lo encuentras en los ajustes de tu cuenta de TMDB.
- **Gemini (04)** · `GEMINI_API_KEY`, desde Google AI Studio.

Git ignora el archivo `.env`.

## Notebooks

Abre el proyecto desde la carpeta del repositorio y selecciona `.venv` como kernel. Ejecuta los notebooks en este orden:

1. [Limpieza](01_ingesta_limpieza.ipynb). Prepara los títulos y los años y guarda `movies_clean.csv`.
2. [Análisis](02_analisis.ipynb). Cruza las películas con las valoraciones y las etiquetas. Las tablas y las respuestas se ven en el notebook.
3. [TMDB](03_tmdb.ipynb). Consulta los datos de diez películas y guarda `movies10.csv`.
4. [Gemini](04_gemini.ipynb). Usa las sinopsis de TMDB y guarda el resultado en `movies10_es.csv`.

Los CSV de salida están en `data/processed/`.

## Qué nos salió

- El catálogo tiene **9.742 películas**. En 13 títulos no pudimos sacar el año.
- Al unir las tablas se mantuvieron las **100.836 valoraciones** y las **3.683 etiquetas**. Encontramos 18 películas sin valoraciones.
- El CSV de TMDB tiene 10 películas. El de Gemini incluye 8 sinopsis en español.
