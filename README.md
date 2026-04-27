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