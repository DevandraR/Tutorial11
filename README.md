# Tutorial 11

<h3>1. Reflection on Hello Minikube</h3>

### Perbandingan Log Aplikasi Sebelum dan Setelah Mengekspos sebagai Layanan

Sebelum aplikasi diekspos sebagai Layanan, mengakses aplikasi biasanya dilakukan dengan menghubungi Pod secara langsung. Log dalam situasi ini akan mencerminkan interaksi khusus dengan koneksi langsung tersebut. Setelah aplikasi diekspos sebagai Layanan dan diakses melalui endpoint Layanan, jumlah entri log akan meningkat setiap kali aplikasi dibuka. Ini terjadi karena Layanan berfungsi sebagai penyeimbang beban yang mengarahkan lalu lintas ke Pod aplikasi. Setiap akses ke aplikasi melalui Layanan menghasilkan entri log baru, yang menunjukkan bahwa permintaan berhasil diterima dan diproses oleh aplikasi melalui Layanan.

### Tujuan Opsi `-n` dalam Perintah `kubectl get`

Opsi `-n` dalam perintah `kubectl get` digunakan untuk menentukan namespace yang ingin ditampilkan. Kubernetes menggunakan namespace untuk mengorganisasi sumber daya dan objek. Ketika `kubectl get` dijalankan tanpa opsi `-n`, perintah ini akan default ke namespace `default` atau namespace yang sedang dikonfigurasi saat itu. Perintah ini hanya akan menampilkan Pod atau Layanan dalam namespace tersebut. Namun, ketika menggunakan opsi `-n kube-system`, perintah ini akan menampilkan sumber daya khusus dalam namespace `kube-system`, yang dikhususkan untuk komponen dan infrastruktur sistem Kubernetes. Output tidak mencantumkan Pod/Layanan yang dibuat secara eksplisit karena kemungkinan berada di namespace `default` atau namespace lain yang digunakan untuk aplikasi, bukan di namespace `kube-system`.
