# Computer-Vision---German-Traffic-Sign
In this project, I make image classification using CNN with German Traffic Sign dataset

## _Project Overview_

Wine merupakan salah satu jenis minuman beralkohol yang banyak dikonsumsi oleh orang-orang di seluruh dunia. Salah satu negara pengekspor wine terbanyak adalah portugal. Untuk mengekspor wine tersebut portugal memerlukan jenis wine yang berkualitas tinggi untuk dijual ke berbagai negara di dunia. Wine yang berkualitas dihasilkan dari sertifikasi dan pengujian yang ketat. Sertifikasi wine umumnya menggunakan pengujian _physicochemical_ dan test sensor seperti kandungan klorida, sulfat, PH, dan lain sebagainya [1]. Data-data pengujian telah banyak didapatkan pada saat pengujian, namun jika ingin menentukan kualitas wine tersebut secara manual maka akan memerlukan waktu yang lama. Sehingga dibuatlah proyek ini untuk menentukan kualitas dari wine berdasarkan data pengujian kualitas wine. This project's use CNN (Convolutional Neural Network) algorithm to train the model.
  
[_Modeling wine preferences by data mining from physicochemical properties_](https://www.sciencedirect.com/science/article/abs/pii/S0167923609001377?via%3Dihub) 

## _Business Understanding_

This project contain the classifi 
Proyek ini berisi pengenalan object gambar dengan melakukan klasifikasi terhadap beberapa rambu lalu lintas. Klasifikasi gambar rambu lalu lintas ini biasa diterapkan pada self-driving cars.

### _Problem Statements_

Masalah yang akan diselesaikan:
- Apakah model yang dibuat menggunakan CNN mampu mengklasifikasikan gambar rambu lalu lintas?

### _Goals_

Tujuan yang ingin dicapai:
- Algoritma yang digunakan adalah CNN atau Convolutional Neural Network karena model tersebut akan mengenali object gambar yang ada pada dataset. Tujuannya agar model CNN yang telah dibuat dapat melakukan klasifi

## _Data Understanding_
Dataset yang digunakan pada proyek ini merupakan dataset mengenai kualitas wine yang diunduh dari UCI Machine Learning Repository Link: (https://archive.ics.uci.edu/ml/machine-learning-databases/wine-quality/).
Berikut beberapa variabel yang terdapat di dalam dataset wine quality UCI Machine Learning Repositories:

| Class Index |               Label Description              | Class Index |                Label Description               |
|:-----------:|:--------------------------------------------:|:-----------:|:----------------------------------------------:|
|      0      | Speed limit (20km/h)                         |      22     | Bumpy road                                     |
|      1      | Speed limit (30km/h)                         |      23     | Slippery road                                  |
|      2      | Speed limit (50km/h)                         |      24     | Road narrows on the right                      |
|      3      | Speed limit (60km/h)                         |      25     | Road work                                      |
|      4      | Speed limit (70km/h)                         |      26     | Traffic signals                                |
|      5      | Speed limit (80km/h)                         |      27     | Pedestrians                                    |
|      6      | End of speed limit (80km/h)                  |      28     | Children crossing                              |
|      7      | Speed limit (100km/h)                        |      29     | Bicycles crossing                              |
|      8      | Speed limit (120km/h)                        |      30     | Beware of ice/snow                             |
|      9      | No passing                                   |      31     | Wild animals crossing                          |
|      10     | No passing for vehicles over 3.5 metric tons |      32     | End of all speed and passing limits            |
|      11     | Right-of-way at the next intersection        |      33     | Turn right ahead                               |
|      12     | Priority road                                |      34     | Turn left ahead                                |
|      13     | Yield                                        |      35     | Ahead only                                     |
|      14     | Stop                                         |      36     | Go straight or right                           |
|      15     | No vehicles                                  |      37     | Go straight or left                            |
|      16     | Vehicles over 3.5 metric tons prohibited     |      38     | Keep right                                     |
|      17     | No entry                                     |      39     | Keep left                                      |
|      18     | General caution                              |      40     | Roundabout mandatory                           |
|      19     | Dangerous curve to the left                  |      41     | End of no passing                              |
|      20     | Dangerous curve to the right                 |      42     | End of no passing by vehicles over 3.5 metric  |
|      21     | Double curve                                 |             |                                                |

Untuk lebih jelasnya data yang terdapat pada dataset tersebut dapat dilihat pada gambar berikut:
![image](https://user-images.githubusercontent.com/62003049/187919809-943dce52-d80d-4dca-84b9-4e2a1cd86bbc.png)

Untuk melihat sebaran data pada dataset, dapat kita lihat melalui data histogram di bawah ini:
![image](https://user-images.githubusercontent.com/62003049/187924117-82c8740e-92dc-4411-8216-d92f82c4608f.png)

Berdasarkan data histogram 'quality' yang merupakan fitur target (label), informasi yang dapat diperoleh yaitu:
- Wine yang terdapat pada dataset didominasi oleh wine yang memiliki kualitas bernilai 5 dan 6
- Distribusi kualitas miring ke kanan (_right-skewed_). Hal ini akan berimplikasi pada model.

## _Data Preparation_
Pada proyek ini dilakukan proses _data preparation_ yaitu:
   Pembagian dataset dengan fungsi train_test_split dari _library_ sklearn Proses pembagian dataset ini bertujuan untuk memisahkan antara data yang akan dilakukan proses training dan data yang akan digunakan untuk pengujian. Tentunya data yang digunakan untuk proses pengujian haruslah data yang belum pernah dilihat oleh model sebelumnya, sehingga proses pemisahan data ini sangat penting.
Berikut ini program yang digunakan pada proses splitting data:
   ![image](https://user-images.githubusercontent.com/62003049/187921201-9c296291-28aa-42c0-a01d-cb8dd769b8ff.png)

## _Modeling_
Model _Machine Learning_ yang digunakan pada proyek ini ada 2 jenis algoritma yang akan dibandingkan berdasarkan hasil prediksi masing-masing algoritma. Algoritma yang pertama digunakan adalah algoritma _random forest_ dan algoritma _boosting_.

Pada Algoritma _Random Forest_, parameter yang digunakan adalah sebagai berikut
- n_estimators=25
- max_depth=32
- random_state=16
- n_jobs=-1
Untuk lebih jelasnya dapat dilihat pada cuplikan kode dibawah ini:
![image](https://user-images.githubusercontent.com/62003049/187921844-cf1c7d27-99dd-4cae-a8ee-86bbd6f497a6.png)

Sedangkan pada Algoritma _Boosting_, parameter yang digunakan adalah sebagai berikut
- learning_rate = 0.05
- random_state = 16
Untuk lebih jelasnya dapat dilihat pada cuplikan kode dibawah ini:
![image](https://user-images.githubusercontent.com/62003049/187921949-c2d1929a-f16c-4980-ae0c-d086ec53fa0f.png)

## _Evaluation_
Model yang telah dibuat dapat memprediksi nilai dari kualitas wine yang ada pada dataset. Karena pada proyek kali ini menggunakan 2 jenis algoritma, maka akan dibandingkan hasil prediksi dari masing-masing algoritma. Metrik yang digunakan pada setiap algoritma adalah MSE atau mean squared error.

Mse merupakan metrik yang menghitung jumlah selisih kuadrat rata-rata nilai sebenarnya dengan nilai prediksi. MSE didefinisikan dalam persamaan berikut:

![image](https://user-images.githubusercontent.com/62003049/187825463-410f0055-ac49-4af8-a56b-a5e280e62eda.png)

Keterangan:
N = jumlah dataset
yi = nilai sebenarnya
y_pred = nilai prediksi

![image](https://user-images.githubusercontent.com/62003049/187925940-3528f511-4845-43e1-a1ac-ba94198998ec.png)

Berdasarkan hasil training model, didapatkanlah jumlah error yang paling kecil adalah _Boosting Algorithm_.

##Conclusion
Proyek pembuatan Sistem Prediksi Kualitas Wine telah berhasil dibuat dengan membandingkan dua metode _supervised learning_-regresi yaitu _Random Forest_ dan _Boosting Algorithm_, dan dapat disimpulkan Algoritma yang memberikan hasil prediksi paling mendekati adalah _Boosting Algorithm_. Hasil prediksi dapat dilihat pada gambar dibawah ini.

![image](https://user-images.githubusercontent.com/62003049/187925821-d12192c4-b4c6-434d-b272-935a66e8af40.png)

##Reference
[1] Cortez, P., Cerdeira, A., Almeida, F., Matos, T., & Reis, J. (2009). Modeling wine preferences by data mining from physicochemical properties. Decision Support Systems, 47(4), 547–553.


