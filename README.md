# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Edutech

* Nama : Mufidatul Ngazizah
* email : mufidatul.ngazizah@gmail.com
* ID : mufidatuln

## Business Understanding
Jaya Jaya Institut merupakan salah satu institusi pendidikan perguruan yang telah berdiri sejak tahun 2000. Hingga saat ini ia telah mencetak banyak lulusan dengan reputasi yang sangat baik. Akan tetapi, terdapat banyak juga siswa yang tidak menyelesaikan pendidikannya alias dropout.

Jumlah dropout yang tinggi ini tentunya menjadi salah satu masalah yang besar untuk sebuah institusi pendidikan. Selain itu, tingkat dropout yang tinggi juga bisa menjadi indikasi bahwa ada masalah mendasar dalam proses penerimaan siswa, pembelajaran, atau dukungan akademik yang disediakan oleh institusi. Oleh karena itu, Jaya Jaya Institut ingin mendeteksi secepat mungkin siswa yang mungkin akan melakukan dropout sehingga dapat diberi bimbingan khusus. 

### Permasalahan Bisnis
Masalah bisnis yang ingin diselesaikan adalah sebagai berikut:
1. Bagaimana cara mengidentifikasi mahasiswa yang berpotensi dropout sejak dini?
2. Apasaja faktor yang menyebabkan siswa tidak menyelesaikan pendidikannya (dropout)?
3. Tindakan apa yang dapat dilakukan untuk mengurangi mahasiswa dropout dan memastikan lebih banyak mahasisawa yang menyelesaikan pendidikannya?

### Cakupan Proyek
Berikut cakupan proyek yang telah dikerjakan:
* Eksplorasi dan Analysis Data : Melakukan eksplorasi pada data yang sudah diperoleh agar dapat mendapatkan gambaran umum tentang data. Selanjutnya melakukan analysis untuk mengidentifikasi faktor yang mempengaruhi mahasiswa dropout
* Visualisasi Data : Membuat dashboard laporan untuk memonitor dan menganalissis mahasiswa yang berpotensi dropout
* Model dan Rekomendasi : Membangun model klasifikasi untuk melakukan rekomendasi yang dapat dilakukan untuk mengurangi droput.

### Persiapan

Sumber Data : [Jaya jaya institute]('data.csv')

**Setup environment**:
Setup environment:
1. Pengguna membuka terminal dengan root yang telah ditentukan
2. Pengguna mengistall virtual env
   
   ```
   py -m pip install virtualenv

   ```

4. Penguna membuat virtual env
   ```
   python -m venv myenv
   ```
   
4. Jalankan virtual env
   ```
   myenv\Script\activate
   ```
   
7. Melakukan install library yang digunakan sesuai requirement.txt
8. Menjalankan jupiter notebook
9. Melakukan input data baru yang ingin diprediksi

**Setup metabase**:

```
docker pull metabase/metabase:v0.46.4
docker run -p 3000:3000 --name metabase metabase/metabase
```

Akses metabase pada http://localhost:3000/setup dan lakukan setup.

**Setup database (supabase)**:

Buat akun dan login https://supabase.com/dashboard/sign-in.
Buat new project
Copy URI pada database setting
Kirim dataset menggunakan sqlalchemy

```
from sqlalchemy import create_engine

URL = "DATABASE_URL"

engine = create_engine(URL)
df.to_sql('dataset', engine)
```


## Business Dashboard
Berikut adalah dashboard yang telah dibuat:

![Dashboard](https://github.com/mufidatuln/Proyek-Menyelesaikan-Permasalahan-Institusi-Pendidikan/blob/main/Dashboard%20Monitoring%20Mahasiswa-1.jpg)



## Menjalankan Sistem Machine Learning
Pada proyek ini telah disediakan sebuah prototype untuk melakukan prediksi terhadap model yang sudah dibuat. Untuk menjalankan protoype secara lokal jalankan perintah berikut di terminal: 

```
streamlit run app.py
```
Atau buka pada tautan [berikut](https://proyek-menyelesaikan-permasalahan-institusi-pendidikan-ec9nqfx.streamlit.app/) untuk membuka prototype yang sudah dijalankan pada streamlit community.
## Conclusion
Jelaskan konklusi dari proyek yang dikerjakan.

### Rekomendasi Action Items
Berikan beberapa rekomendasi action items yang harus dilakukan perusahaan guna menyelesaikan permasalahan atau mencapai target mereka.
- action item 1
- action item 2
