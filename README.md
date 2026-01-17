# Employee Technical Efficiency Mapping (DEA Model)

## 📌 Project Overview
Proyek ini menggunakan metode **Data Envelopment Analysis (DEA)**. Melalui DEA, kita bisa memetakan efisiensi setiap karyawan apakah sudah berada pada titik optimal atau masih ada *slack* sehingga masih ada ruang pengoptimalan. Prinsip DEA adalah mengukur efisiensi berdasarkan input (investasi yang diberikan) dan output (hasil kerja) yang kemudian dilakukan perbandingan relatif antar *Decision Making Unit* (DMU). Sekilas tentang proyek ini:
* **Sumber Dataset:** [Kaggle](https://www.kaggle.com/code/shifanaaz125/hr-dataset-eda/input).
* **Metode Analisis:** *Data Envelopment Analysis* (DEA).
* **Alat yang digunakan:** Excel, Python (Google Colab), Tableau.
* ***Input*:** Gaji, Frekuensi Pelatihan, dan Lama Bekerja (Variabel: *MonthlyIncome*, *TrainingTimesLastYear*, *TotalWorkingYears*).
* ***Output*:** Skor Performa Karyawan, Level Pekerjaan, dan Persentase Kenaikan Gaji (Variabel: *PerformanceRating*, *JobLevel*, *PercentSalaryHike*).

---

## 📌 Data Envelopment Analysis (DEA)
Analisis ini menggunakan pendekatan ilmiah dengan parameter spesifik:

1.  ***Input-Oriented Model*:** Fokus pada ***Cost Optimization***. Model ini mengidentifikasi bagaimana perusahaan dapat mengoptimalkan *input* tanpa menurunkan standar kualitas *output*. Pemilihan orientasi *input* dibandingkan *output* didasarkan pada konteks bahwa lebih realistis bagi perusahaan memiliki kontrol lebih besar terhadap *input* (seperti gaji) dibandingkan kontrol langsung terhadap *output* (seperti *performance rating* yang dipengaruhi banyak faktor eksternal dan subjektivitas).
2.  **VRS (*Variable Returns to Scale*):** Memberikan penilaian lebih adil karena hubungan *input* dan *output* pada proyek ini tidak linear. Hal ini sejalan dengan konsep *diminishing returns*.
3.  DEA dalam proyek ini menghasilkan skor efisiensi teknis untuk setiap DMU (karyawan). Penggunaan efisiensi teknis murni mengukur performa operasional tanpa terpengaruh harga pasar atau fluktuasi ekonomi luar. Dengan demikian, perusahaan dapat mengidentifikasi karyawan yang mampu mencapai *frontier* (batas performa terbaik, skor VRS=1) dan mendeteksi *slack* (pemborosan *input*) pada karyawan yang memiliki skor VRS dibawah 1, sehingga intervensi manajerial dapat dilakukan secara presisi. 

---

## 📌 Employee Efficiency Categorization
Dalam proyek ini, saya mengelompokkan karyawan ke dalam 4 kategori strategis berdasarkan skor **DEA (VRS)**

* ***The Benchmarks* (skor efisiensi VRS: 1.0):** Karyawan standar emas. Dalam proyek ini, seorang karyawan dikategorikan efisien (*The benchmarks*) apabila ia mampu menghasilkan kombinasi *output* yang maksimal, yaitu: meraih *performance rating* yang tinggi, menduduki *job level* yang strategis, serta mendapatkan *percent salary hike* sebagai bentuk apresiasi dan pengakuan finansial yang optimal dari perusahaan.
* - Pencapaian tersebut berhasil diraih dengan penggunaan *input* yang efisien, yang diukur melalui nilai *monthly income* (gaji), *training times* (frekuensi pelatihan), dan *total working years* (lama bekerja) dibandingkan dengan rekan kerja lainnya dalam kelompok skala yang setara.
* ***High Performers* (skor efisiensi VRS: 0,80-0,99):** Hasil kerja tinggi, namun biaya yang dikeluarkan perusahaan (gaji/fasilitas) jauh lebih besar dibandingkan dengan *The Benchmarks*.
* ***Well Performers* (skor efisiensi VRS: 0,65-0,79):** Hasil kerja bagus, namun masih bisa dioptimalkan lebih pada *input* yang diberikan. 
* ***Latent Potential* (skor efisiensi VRS: 0,50-0,64):** Butuh pendampingan. Memiliki potensi namun efisiensinya jauh belum optimal. 
* ***Urgent Attention* (skor efisiensi VRS: < 0.50):** Perlu atensi (audit performa) segera. *input* tinggi, namun performa *output* rendah. 

---

## 📊 Dashboard Analysis & Key Insights 

### **Dashboard 1: Departmental Efficiency & Profile (Macro View)**
* **VRS *Efficiency Score*:**
* - Rata-rata efisiensi teknis perusahaan adalah **0,6585**, mengindikasikan potensi optimasi *input* sebesar **~34%**.
  - Selain itu, perusahaan didominasi oleh karyawan dengan kategori *latent potential* dan *urgent attention*. Hal ini menandakan perlu adanya perhatian lebih pada karyawan.
* ***Efficiency vs Attrition* (*Brain Drain Alert*):**
* - Ditemukan paradoks di mana kelompok ***the benchmarks*** justru memiliki persentase *attrition: no* paling kecil dibandingkan kelompok lain.
  - Ini dapat dianggap sebagai suatu sinyal **brain drain**, dimana talenta terbaik perusahaan justru memiliki risiko pengunduran tinggi tertinggi.
* ***Demographic Profile*:**
* - Karyawan pada **tahun ke-5 masa kerja** menjadi titik kritis penumpukan status *urgent attention*.
  - Secara usia, kelompok **Dewasa Awal (26-35 tahun)** mendominasi kategori inefisien.
* ***Latent Potential Group* (*The Transition Phase*):**
* - Kelompok ini memiliki jangkauan masa kerja (*years at company*) paling luas di grafik.
  - Hal ini mengartikan adanya kecenderungan bahwa mereka adalah karyawan dalam fase transisi (seperti karyawan baru yang sedang beradaptasi atau karyawan lama yang berpindah peran), sehingga efisiensi mereka belum stabil. Namun, mereka memiliki peluang besar untuk naik ke kategori *the benchmarks* dengan pendekatan yang tepat.
* ***Behavioral & Health*:**
* - Analisis kepuasan kerja menunjukkan kelompok *well performers* memiliki profil ekstrem dimana mereka mendominasi skor kepuasan tertinggi (Skala 4) sekaligus ketidakpuasan terendah (Skala 1).
  - *The benchmarks* teridentifikasi sebagai kelompok paling stabil dengan tingkat ketidakpuasan terendah. Hal ini ditunjukkan dengan grafik aspek *Work-Life Balance* (WLB), dimana kualitas hidup terbaik (Skala 4) dipimpin oleh *the benchmarks* teridentifikasi sebagai kelompok paling stabil dengan tingkat ketidakpuasan terendah. Hal ini ditunjukkan dengan grafik aspek *Work-Life Balance* (WLB), dimana kualitas hidup terbaik (Skala 4) dipimpin oleh *the benchmarks* dan *latent potential*, sedangkan *high performers* berada di posisi terbawah yang menandakan indikasi risiko *burnout* akibat mengejar *output*.
  - Keluhan WLB terendah (Skala 1) didominasi pada *latent potential* dan *urgent attention*. Hal ini memperkuat indikasi bahwa inefisiensi berkaitan erat dengan masalah manajemen waktu.

### **Dashboard 2: Cost vs Performance Analysis (Micro View)**
* ***Income vs Performance* (*Cost Leakage*):** Terdeteksi kebocoran biaya pada status ***high performers***. Mereka menerima *Avg. Monthly income* hampir **10K**, dimana lebih tinggi dibandingkan *the benchmarks* namun tingkat performanya sedikit di bawah kelompok *the benchmarks* yang gajinya lebih efisien.
* ***Training ROI Paradox*:** Kelompok ***urgent attention*** menerima investasi pelatihan tertinggi (rata-rata **>3 sesi per tahun**) dibandingkan kelompok lainnya. Namun, investasi ini belum menghasilkan pengembalian berupa tingkat efisiensi karyawan yang lebih bagus. 
* ***Actionable Employee List*:** Tabel yang memudahkan perusahaan untuk melihat skor efisiensi per ID karyawan sehingga memudahkan intervensi lanjutan.
  
---

## 💡 Strategic Recommendations
1.  **Retention Priority:** Meluncurkan program retensi khusus untuk kelompok ***the benchmarks*** guna mencegah kehilangan aset paling efisien perusahaan.
2.  **Training Evaluation:** Meninjau kembali kurikulum pelatihan bagi kelompok ***urgent attention***.  Melihat adanya paradoks dimana kelompok *urgent attention* yang justru memliki pelatihan tertinggi malah mencapai skor efisiensi yang rendah. Selain itu, coba untuk memperhatikan *engagement* atau beban kerja (*burnout*).
3.  **1on1 session:** Melakukan sesi tatap muka personal dengan karyawan untuk diskusi perkembangan dan aspirasi, terutama pada kelompok *urgent attention*. Hal ini ditujukan untuk menciptakan *safe space*, meningkatkan *engagement*, dan mengumpulkan *feedback* kualitatif yang akan dijadikan bahan agar efisiensi karyawan dapat lebih optimal.

---

## 🔗 Live Dashboard
Melalui *dashboard* ini, kita bisa melihat skor efisiensi secara agregat (perusahaan) atau spesifik (per departemen). Dashboard ini saya rancang untuk memudahkan pimpinan dalam mengidentifikasi departemen mana yang membutuhkan optimasi input paling segera.
[KLIK UNTUK MELIHAT INTERACTIVE DASHBOARD](https://public.tableau.com/app/profile/aisyahlani.mulyawati/viz/DEA_2NDProjectAisyahlani/Dashboard1)
