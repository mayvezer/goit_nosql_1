# Spotify Tracks Analysis with MongoDB

Проєкт призначений для завантаження, трансформації та аналізу великого масиву даних треків Spotify (близько 114k записів) за допомогою Python (`pandas`, `pymongo`) та NoSQL бази даних MongoDB Atlas.

---

## 1. Архітектура та структура даних

Проєкт реалізує двоетапну архітектуру зберігання даних:
1. **`tracks_raw`** — колекція "сирих" (raw) даних, куди завантажується оригінальний CSV-датасет після мінімальної конвертації типів.
2. **`tracks`** — очищена та структурована колекція, отримана за допомогою агрегаційного конвеєра MongoDB (`Aggregation Pipeline`).

### Приклад структури документа в колекції `tracks`:
```json
{
  "track_id": "11dFghVXANMlKmJXs3bNl4",
  "name": "Prisioneros",
  "artists": ["Kinky"],
  "album_name": "Kinky",
  "popularity": 45,
  "duration_ms": 215000,
  "explicit": false,
  "genres": ["alternative", "latin"],
  "audio_features": {
    "danceability": 0.72,
    "energy": 0.85,
    "key": 2,
    "loudness": -4.5,
    "mode": 1,
    "speechiness": 0.05,
    "acousticness": 0.12,
    "instrumentalness": 0.0,
    "liveness": 0.1,
    "valence": 0.65,
    "tempo": 120.5,
    "time_signature": 4
  },
  "duration_sec": 215.0,
  "popularity_tier": "medium"
}
