## Tutorial 8 - Publisher

#### Commit 1 Reflection
#### 1. How many data your publlsher program will send to the message broker in one run?
Dalam satu kali jalannya program, ada 5 data yang di-publish oleh program ke message broker. Hal ini dapat dilihat dari function main() yang memanggil publish_event() sebanyak 5 kali, di mana satu data dikirimkan setiap kali publish_event() dipanggil. 

#### 2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
Program publisher dan program subscriber memiliki url yang sama karena kedua program dikonfigurasi untuk terhubung ke satu message broker yang sama untuk berkomunikasi. Dalam kasus ini, program publisher akan mengirimkan data ke queue, sedangkan program subscriber akan mengatur listener untuk menerima data dari queue tersebut. Oleh karenanya, kedua program harus memiliki url yang sama agar komunikasi dapat berjalan.

#### Commit 2 Screen Capture
Running RabbitMQ Screen Capture
![Running RabbitMQ Screen Capture](/images/running_rabbitmq.png)

#### Commit 3 Screen Capture and Reflection
Sending and Processing Event Screen Capture
![Sending and Processing Event Screen Capture](/images/sending_and_processing_event.png)

Setelah program publisher di-run, semua data dalam program publisher akan dikirimkan ke message queue. Kemudian, program subscriber yang terhubung ke message queue yang sama akan menampilkan seluruh data yang telah dikirimkan tadi di console.

#### Commit 4 Screen Capture and Reflection
Monitoring Chart Screen Capture
![Monitoring Chart](/images/monitoring_chart.png)

Spike yang muncul pada chart di atas menunjukkan adanya peningkatan message rates. Hal ini bisa terjadi karena program publisher yang di-run berulang kali akan secara tidak langsung meningkatkan jumlah message yang dikirimkan. Alhasil, terjadi spike pada RabbitMQ sebagai message queue.