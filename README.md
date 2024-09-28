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
Proyek ini bertujuan untuk mengatasi masalah utama yang dihadapi Jaya Jaya Institut terkait tingkat dropout siswa. Berikut adalah rangkuman proyek ini:

1. Bagaimana cara mengidentifikasi siswa yang berpotensi dropout sejak awal?

- Dengan mengembangkan model prediktif berbasis algoritma seperti Random Forest, Desesion Tree maupun algoritma XGBoost Jaya Jaya Institut dapat mengenali siswa yang berisiko dropout lebih dini. Model ini mampu mendeteksi siswa berisiko dengan tingkat akurasi yang baik berdasarkan data historis serta faktor-faktor yang berkaitan.
  
2. Apasaja faktor yang menyebabkan siswa tidak menyelesaikan pendidikannya (dropout)?
- Faktor yang paling berpengaruh terhadap keputusan mahasiswa untuk dropout berdasarkan analisis korelasi dan penilaian fitur dalam model prediktif menunjukkan bahwa latar belakang akademik (seperti nilai dan jumlah mata kuliah yang diambil) serta kondisi ekonomi (seperti beasiswa atau keadaan sosial-ekonomi yang kurang stabil). Contohnya siswa yang mengalami kesulitan akademik pada semester awal cenderung memiliki risiko dropout lebih tinggi.

3. Tindakan apa yang dapat dilakukan untuk mengurangi mahasiswa dropout dan memastikan lebih banyak mahasisawa yang menyelesaikan pendidikannya?

- Jaya Jaya Institut dapat mengurangi mahasiswa dropout dan memastikan lebih banyak mahasisawa yang menyelesaikan pendidikannya dengan beberapa strategi berdasarkan temuan dari model dan analisis data. Hal yang dapat dilakukan dengan menyesuaikan kurikulum untuk mengurangi beban siswa, menyediakan bimbingan akademik yang lebih intensif, dan memberikan dukungan finansial tambahan kepada siswa yang membutuhkan atau berprestasi. Analisa lebih dini dengan data dapat membantu memastikan lebih banyak siswa menyelesaikan pendidikan mereka.

### Rekomendasi Action Items
Berikan beberapa rekomendasi action items yang harus dilakukan perusahaan guna menyelesaikan permasalahan atau mencapai target mereka.
Bimbingan Akademik yang Intensif:

1. Sediakan sesi bimbingan akademik lebih intensif, terutama bagi mahasiswa yang berada dalam semester awal dan yang memiliki nilai rendah. Fokus pada memberikan dukungan di bidang yang mereka kesulitan. Mahasiswa yang mengalami masalah akademik dan pribadi, seperti yang tercermin dari faktor status pernikahan, mungkin memerlukan dukungan psikologis lebih besar. Universitas dapat menyediakan layanan konseling atau workshop terkait manajemen stres dan keterampilan belajar
   
2. Gunakan data dari analisis dropout (seperti yang terlihat dari marital status, beasiswa, atau hasil akademik) untuk mengidentifikasi mahasiswa berisiko sejak awal. Intervensi dapat dilakukan melalui konseling atau memberikan akses lebih besar ke sumber daya belajar. Buat sistem monitoring berkala untuk melihat perkembangan akademik setiap mahasiswa. Mahasiswa yang terdeteksi mengalami penurunan performa atau memiliki tanda-tanda ingin dropout dapat segera diintervensi dengan cara yang tepat.
   
3. Berdasarkan analisis penerima beasiswa, universitas perlu meningkatkan dukungan finansial, terutama bagi mahasiswa dari keluarga dengan kondisi ekonomi sulit. Tambahkan skema beasiswa atau bantuan biaya pendidikan.
   
4. Kurangi beban akademik untuk mahasiswa dengan kinerja rendah, terutama di semester awal. Misalnya, menawarkan pilihan untuk mengambil lebih sedikit mata kuliah atau memberikan opsi remedial untuk mata kuliah yang paling sering diambil oleh mahasiswa dropout, seperti yang teridentifikasi di dashboard.
   
5. Berdasarkan data mata kuliah yang paling sering diambil mahasiswa dropout (seperti Management dan Nursing), universitas dapat mereview kembali metode pengajaran dan beban kerja pada mata kuliah ini. Ini dapat berupa perubahan metode pengajaran, pengurangan beban kurikulum, atau menawarkan lebih banyak sumber belajar tambahan.


