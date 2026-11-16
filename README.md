# 🌍 Google Earth Engine — NEXORA

Project untuk analisis spasial menggunakan **Google Earth Engine (GEE)** API.

## 📋 Ringkasan Proyek

Platform ini bertujuan untuk:
- Analisis kemiringan lereng (slope mapping) dari data DEM
- Klasifikasi tutupan lahan (land cover classification)
- Visualisasi peta spasial interaktif
- Ekspor hasil ke format SHP (Shapefile) dan PDF

## 🛠️ Tech Stack

| Komponen | Teknologi |
|----------|-----------|
| Backend | Python 3.12 + FastAPI |
| GEE Client | `earthengine-api` (Python) |
| Geospatial | `rasterio`, `geopandas`, `rioxarray`, `shapely`, `pyproj` |
| Visualization | `matplotlib`, ` Folium` (interactive maps) |
| Export | `rasterio` → GeoTIFF, ` geopandas` → SHP, `ReportLab` → PDF |

## 📁 Struktur Folder

```
google-earth-engine/
├── src/
│   ├── slope_mapper.py      # Hitung kemiringan lereng dari DEM
│   ├── land_classifier.py   # Klasifikasi tutupan lahan
│   ├── export_shp.py        # Export ke Shapefile
│   └── export_pdf.py        # Generate peta layout PDF
├── notebooks/
│   └── slope_analysis.ipynb # Jupyter notebook prototype
├── config/
│   └── gee_credentials.json # Service account credentials (git-ignored)
├── requirements.txt
├── .env.example
└── README.md
```

## 🚀 Quick Start

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Authenticate GEE
```bash
python -c "import ee; ee.Authenticate()"
python -c "import ee; ee.Initialize()"
```

### 3. Jalankan Slope Mapper
```bash
python -m src.slope_mapper --area "Bandung Barat" --output ./output
```

## 🔐 Environment Variables

Buat file `.env` dari `.env.example`:
```bash
GEE_SERVICE_ACCOUNT=email@project.iam.gserviceaccount.com
GEE_PRIVATE_KEY="-----BEGIN RSA PRIVATE KEY-----\n..."
```

Atau gunakan OAuth user-based auth (lebih sederhana untuk personal use).

## 📄 Output Format

- **GeoTIFF**: Raster slope/hydrology layer
- **Shapefile (.shp)**: Vektor polygon per kelas lereng
- **PDF**: Peta layout siap cetak dengan legend, scale, north arrow

## 📌 Roadmap

- [x] Setup repository & struktur proyek
- [ ] Integrasi GEE Python API
- [ ] Slope mapper dari SRTM/ASTER DEM
- [ ] Land cover classifier (Sentinel-2)
- [ ] Export SHP + PDF batch
- [ ] Web dashboard (FastAPI + Leaflet)
- [ ] Integration dengan NexoraGIS platform

---

*Dikembangkan oleh NEXORA AI Team*
*Powered by Google Earth Engine*
