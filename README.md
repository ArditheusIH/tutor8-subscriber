1. What is ampq? <br/>
Advanced Message Queuing Protocol (AMPQ) adalah open-standard protocol untuk berkomunikasi seperti mengirimkan pesan atau data antar aplikasi atau komponen lain secara asinkronus <br/>

2. What it means? guest:guest@localhost:5672 , what is the first guest, and what is
the second guest, and what is localhost:5672 is for? <br/>
guest:guest merupakan representasi dari username:password, jadi guest yang pertama (sebelum titik dua) adalah username dan guest yang kedua (setelah titik dua). Localhost:5672 menunjukkan IP Address dari jalannya server program. Localhost menandakan bahwa server saat ini berjalan di mesin tempat kode sedang dijalankan sedangkan 5672 merupakan port number untuk komunikasinya <br/>

![alt text](/spike2.png)


![alt text](/reduced.png)

Ketika menjalankan 3 instance Subscriber, terlihat bahwa jumlah queued message turun lebih cepat jika dibandingkan dengan hanya menggunakan satu Subscriber. Hal ini terjadi karena adanya distribusi message secara paralel oleh Subscriber. Jika satu subscriber sedang delay sedangkan masih ada message yang harus diterima, maka Subscriber yang tidak sedang delay dapat menerima message tersebut. Hal ini yang disebut dengan event driven, dimana event yang muncul hanya akan diproses oleh yang berminat saja tanpa menunggu apapun.