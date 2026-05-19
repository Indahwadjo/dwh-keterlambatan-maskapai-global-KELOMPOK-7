# Global Flight Analytics: Data Warehouse untuk Pemantauan dan Analisis Lalu Lintas Udara Dunia Berbasis OpenSky Network-KELOMPOK-7
Project Data Warehouse analisis keterlambatan, kapasitas penumpang, dan rute maskapai global menggunakan OpenSky API
# Global Flight Analytics

## Deskripsi Project
Project ini bertujuan membangun sistem Data Warehouse berbasis penerbangan global untuk melakukan analisis:
- Keterlambatan penerbangan
- Kepadatan trafik udara
- Aktivitas maskapai
- Rute penerbangan
- Distribusi aktivitas bandara global

Data diperoleh dari OpenSky Network API yang menyediakan data penerbangan secara real-time dalam format JSON.

## Dataset / API
OpenSky Network States API:
https://opensky-network.org/api/states/all

Dokumentasi API:
https://openskynetwork.github.io/opensky-api/rest.html

## Tahapan Project
1. Mengambil data penerbangan global dari OpenSky Network API menggunakan python.

2. Menyimpan raw JSON data ke staging area sebagai temporary storage.

3. Melakukan proses transformasi data:
   - Handling missing value
   - Filtering data tidak valid
   - Konversi timestamp
   - Standarisasi atribut
   - Agregasi data penerbangan

4. Membentuk struktur star schema yang terdiri atas:
   - fact_flight_activity
   - dim_time
   - dim_airline
   - dim_airport
   - dim_route
   - dim_country

5. Memasukkan data hasil transformasi ke PostgreSQL Data Warehouse.

6. Membentuk OLAP Cube menggunakan Atoti untuk mendukung:
   - drill-down
   - roll-up
   - slicing
   - dicing

7. Membuat dashboard visualisasi untuk menampilkan insight terkait:
   - Keterlambatan penerbangan
   - Aktivitas bandara
   - Trafik udara global
   - Pola rute maskapai
