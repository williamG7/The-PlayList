# The PlayList - Clasificador de Géneros Musicales de Spotify

![Spotify](https://musiccustodian.com/wp-content/uploads/2025/01/Spotify.jpg)

## Descripción

Proyecto de **Machine Learning** que implementa un modelo de **regresión logística** para clasificar canciones de Spotify en 6 géneros musicales diferentes, basándose en sus características acústicas y musicales.

Este proyecto fue desarrollado originalmente en **Google Colab** y analiza un dataset de **32,000 canciones** con diversos atributos musicales proporcionados por la API de Spotify.

## Objetivo

Crear un modelo de clasificación capaz de determinar el género musical de una canción utilizando únicamente sus características técnicas (bailabilidad, energía, tempo, etc.), sin considerar información contextual como el artista o el nombre de la canción.

## Dataset

El proyecto utiliza el dataset [Spotify Songs](https://raw.githubusercontent.com/raimonizard/datasets/refs/heads/main/spotify_songs_sub.csv) que contiene:

- **32,833 canciones**
- **18 columnas** con diferentes atributos
- **6 géneros musicales**: Pop, Rap, Rock, Latin, R&B, EDM

### Características del Dataset

| Característica | Descripción |
|---------------|-------------|
| `track_artist` | Nombre del artista |
| `danceability` | Índice de bailabilidad (0-1) |
| `energy` | Energía de la canción (0-1) |
| `key` | Tonalidad musical |
| `loudness` | Volumen/graves de la canción |
| `mode` | Modo musical (mayor/menor) |
| `speechiness` | Cantidad de palabra hablada/cantada |
| `acousticness` | Nivel acústico de la grabación |
| `instrumentalness` | Proporción instrumental |
| `liveness` | Probabilidad de grabación en vivo |
| `valence` | Positividad musical |
| `tempo` | Tempo en BPM |
| `track_popularity` | Popularidad de la canción |
| `song_genre` | **Variable objetivo** - Género musical |

### Distribución de Géneros

| Género | Cantidad de Canciones | Porcentaje |
|--------|----------------------|------------|
| EDM | 6,043 | ~18.4% |
| Rap | 5,746 | ~17.5% |
| Pop | 5,507 | ~16.8% |
| R&B | 5,431 | ~16.5% |
| Latin | 5,155 | ~15.7% |
| Rock | 4,951 | ~15.1% |

## Metodología

### 1. **Análisis Exploratorio de Datos (EDA)**
- Inspección de la estructura del dataset
- Identificación de valores nulos (15 valores en total)
- Análisis de correlaciones entre variables
- Visualización de distribuciones por género y artista
- Análisis temporal de publicaciones

### 2. **Preprocesamiento**
- **Selección de features**: Se utilizan solo las características musicales cuantitativas
- **Encoding**: Mapeo de géneros musicales a valores numéricos (0-5)
- **Escalado**: Normalización de datos usando `MinMaxScaler` para mejorar la convergencia

### 3. **Modelado**
- **Algoritmo**: Regresión Logística
- **Variables independientes (X)**: 12 características musicales
- **Variable dependiente (y)**: `song_genre` (codificada)

### 4. **Evaluación**
- Métricas de precisión
- Matriz de confusión
- Análisis de rendimiento por género

## Tecnologías Utilizadas

```python
- Python 3.x
- pandas
- numpy
- seaborn
- matplotlib
- scikit-learn
- MinMaxScaler
- LogisticRegression
- accuracy_score
- confusion_matrix
```

## Estructura del Proyecto

```
The-PlayList/
│
├── The_Playlist_GuzmanWilliam.ipynb    # Notebook principal con todo el análisis
├── README.md                            # Este archivo
```

## Uso

### Opción 1: Google Colab (Recomendado)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/williamG7/The-PlayList/blob/main/The_Playlist_GuzmanWilliam.ipynb)

### Opción 2: Local

1. **Clonar el repositorio**
```bash
git clone https://github.com/williamG7/The-PlayList.git
cd The-PlayList
```

2. **Instalar dependencias**
```bash
pip install pandas numpy seaborn matplotlib scikit-learn
```

3. **Ejecutar el notebook**
```bash
jupyter notebook The_Playlist_GuzmanWilliam.ipynb
```

## Resultados Principales

### Insights del EDA
- **Artista con más canciones**: Martin Garrix (161 canciones)
- **Año con más publicaciones**: 2019 (9,079 canciones)
- **Promedio de canciones por artista**: ~3.07
- **Total de artistas únicos**: 10,692

### Correlaciones Destacadas
El análisis de correlación reveló relaciones importantes entre variables como:
- Energy vs. Loudness
- Acousticness vs. Energy
- Valence vs. Danceability

## Aprendizajes

Este proyecto demuestra:
- ✅ Importancia del preprocesamiento en Machine Learning
- ✅ Aplicación práctica de regresión logística multiclase
- ✅ Análisis exploratorio de datos musicales
- ✅ Visualización efectiva de datos
- ✅ Escalado de features para mejor convergencia

## 👤 Autor

**William Guzmán**
- GitHub: [@williamG7](https://github.com/williamG7)

## 📝 Licencia

Este proyecto está disponible bajo la licencia MIT. Siéntete libre de usar, modificar y distribuir este código.

---

⭐ Si este proyecto te fue útil, considera darle una estrella en GitHub!
