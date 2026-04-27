## Test Plan 1: `/all-student`

Endpoint `/all-student` diuji menggunakan JMeter untuk melihat performa aplikasi ketika mengambil seluruh data student.

![Hasil JMeter All Student](images/all-student.png)

## Test Plan 2: `/all-student-name`

Endpoint `/all-student-name` diuji menggunakan JMeter untuk melihat performa aplikasi ketika hanya mengambil nama student.

![Hasil JMeter All Student Name](images/all-student-name.png)

## Test Plan 3: `/highest-gpa`

Endpoint `/highest-gpa` diuji menggunakan JMeter untuk melihat performa aplikasi ketika mengambil satu student dengan GPA tertinggi.

![Hasil JMeter Highest GPA](images/highest-gpa.png)

## Kesimpulan Singkat

Berdasarkan pengujian dengan JMeter, setiap endpoint dapat dibandingkan dari sisi waktu respons dan latency. Endpoint yang mengambil data lebih banyak, seperti `/all-student`, umumnya membutuhkan waktu lebih lama dibanding endpoint yang hanya mengambil sebagian data atau satu data tertentu, seperti `/all-student-name` dan `/highest-gpa`.

## Pengujian Melalui Command Line

Selain menggunakan GUI, test plan juga dijalankan melalui command line menggunakan mode non-GUI. Mode ini lebih ringan dan cocok digunakan untuk menyimpan hasil pengujian secara otomatis dalam file `.jtl`.

Command yang digunakan:

```bash
jmeter -n -t test_plan_1.jmx -l results1.jtl
jmeter -n -t test_plan_2.jmx -l results2.jtl
jmeter -n -t test_plan_3.jmx -l results3.jtl

## Hasil Pengujian 1: Endpoint `/all-student`

Pengujian pertama dilakukan pada endpoint `/all-student`. Endpoint ini digunakan untuk mengambil seluruh data student yang tersedia di database. Karena data yang dikembalikan cukup besar, endpoint ini berpotensi memiliki waktu respons yang lebih tinggi dibanding endpoint lain.

Hasil pengujian menunjukkan bahwa request berhasil dijalankan oleh JMeter dan hasilnya tersimpan pada file `results1.jtl`.

![Result 1 - All Student](images/results1.png)

## Hasil Pengujian 2: Endpoint `/all-student-name`

Pengujian kedua dilakukan pada endpoint `/all-student-name`. Endpoint ini digunakan untuk mengambil daftar nama student saja, sehingga data yang dikembalikan lebih ringan dibandingkan `/all-student`.

Hasil pengujian menunjukkan bahwa request berhasil dijalankan melalui JMeter. Output hasil pengujian disimpan pada file `results2.jtl`, yang berisi informasi seperti elapsed time, response code, status success, jumlah bytes, latency, dan thread name.

![Result 2 - All Student Name](images/results2.png)

## Hasil Pengujian 3: Endpoint `/highest-gpa`

Pengujian ketiga dilakukan pada endpoint `/highest-gpa`. Endpoint ini digunakan untuk mengambil data student dengan GPA tertinggi. Berdasarkan hasil command line JMeter, seluruh request berhasil dijalankan dengan response code `200` dan error rate `0.00%`.

Pada screenshot `results3`, terlihat bahwa file `results3.jtl` berisi hasil request untuk endpoint `/highest-gpa`. Setiap baris menunjukkan hasil satu request, termasuk waktu eksekusi, label request, response code, status success, dan URL endpoint yang diuji.

![Result 3 - Highest GPA](images/results3.png)