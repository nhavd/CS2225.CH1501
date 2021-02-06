# NHẬN DẠNG HÀNH ĐỘNG BẠO LỰC QUA VIDEO 
GROUP N009: [Pham Duc Duy](duypd.13@grad.uit.edu.vn ) - [Dong Dang Khoa](khoadd.14@grad.uit.edu.vn) - [Vo Dinh Nha](nhavd.14@grad.uit.edu.vn)

## License [![GitHub license](https://img.shields.io/github/license/Naereen/StrapDown.js.svg)](https://github.com/Naereen/StrapDown.js/blob/master/LICENSE)


## Violence Detection [![made-with-python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg)](https://www.python.org/) [![Open In Collab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com)
Là mục tiêu đề tài mà nhóm đã thảo luận và đưa ra ý kiến thống nhất

Để thực hiện và hoàn thành project, nhóm N009 đã lựa chọn phương pháp nhận diện hành động bạo lực bằng việc kết hợp giữa Convolution Neural Networks và Long Short Term Memory.

- [Violence_detection.ipynb](https://github.com/nhavd/CS2225.CH1501/blob/master/Violence%20Detection/Violence_detection.ipynb): Cài đặt mô hình
- [ViolenceDetection_RootDataset.h5](https://drive.google.com/drive/folders/1af1PtjjSYbQG8keQ--QoTEAWpzerzFt_?usp=sharing): Model file
- [Predictor.ipynb](https://github.com/nhavd/CS2225.CH1501/blob/master/Violence%20Detection/Predictor.ipynb): Kiểm thử mô hình trên tập dữ liệu mới 

## Kết quả nhận diện mong muốn từ giải pháp
![](images/result1.png)

## Project timeline

**`07-09-2020`**: Thảo luận ý tưởng, tìm kiếm các đề tài mong muốn liên quan đến môn học.

**`15-09-2020`**: Thống nhất ý tưởng, viết mô tả đề tài

**`10-10-2020`**: Thảo luận nhóm về đề tài, tìm kiếm, tổng hợp các tài liệu tham khảo

**`30-11-2020`**: Nhóm học tập hoàn thành việc tìm hiểu các kiến thức cơ bản liên quan đề tài, chạy thử nghiệm 1 số demo

**`13-12-2020`**: Họp nhóm, xây dựng các phiên bản mã nguồn 

**`27-12-2020`**: Merge mã nguồn

**`10-01-2021`**: Họp nhóm, Viết báo cáo, chuẩn bị các resource cần thiết 

**`31-01-2021`**: Họp nhóm, thống nhất chỉnh sửa mã nguồn, báo cáo. 

**`06-02-2021`**: Hoàn tất bài báo cáo, chuẩn bị submit

## Nội dung trình bày
*********************************************************************************************
*[1. Mô tả bài toán](#mô-tả-bài-toán)*

*- [Giới thiệu](#giới-thiệu)*

*- [Phân loại bài toán](#phân-loại-bài-toán)*

*[2. Phương pháp giải quyết bài toán](#phương-pháp-giải-quyết-bài-toán)*

*[3. Vấn đề về dữ liệu](#vấn-đề-về-dữ-liệu)*

*[4. Thực thi](#thực-thi)*

*[5. Kết quả](#kết-quả)*

*[6. Đánh giá](#đánh-giá)*

*[7. Datasets](#datasets)*
*********************************************************************************************

## Mô tả bài toán

### Giới thiệu

Ngày nay, bạo lực xảy ra khắp nơi với rất nhiều lý do xã hội. Ứng dụng công nghệ góp phần hạn chế bạo lực xảy ra bằng việc sử dụng các camera an ninh, giám sát 24/7 tại các địa điểm nóng. Cùng với đó, 1 lượng lớn videos được tạo ra mỗi giây, đòi hỏi các giám sát viên liên lục theo dõi trên màn hình, như vậy không hiệu quả. Để giải quyết 1 trong các bài toán tương tự, Deep learning ra đời, nó có thể tự động phát hiện các bất thường một cách nhanh chóng. Ta có thể ứng dụng để trích xuất các đoạn video bất thường (ở đề tài này là các đoạn video có chứa hành vi bạo lực), đưa qua các thuật toán để đánh giá chính xác hơn, kết quả nhận được là cảnh báo video có chứa hành động bạo lực hay không.

Cụ thể trong đồ án này, ta có input là một đoạn video, khi đi qua bộ nhận dạng ta sẽ nhận được kết quả đánh giá về video, có hay không bạo lực.

- <b>Input</b>: Đoạn video

- <b>Output</b>:Nhãn thông báo video có chứa hành động bạo lực hay không

- <b>Hướng tiếp cận</b>: Phương pháp giải bài toán chỉ giới hạn ở việc nhận diện hành động bạo lực. Trong đó khi ảnh/video được upload lên thì các khung hình sẽ được trích xuất, đồng thời thuật toán trong mô hình huấn luyện sẽ quét qua tất cả các hình này và nhận diện xem có hành động bạo lực hay không?

- <b>Giới hạn</b>: Số lượng đối tượng trong 1 khung ảnh < 10, ít chồng lấn. Tập dữ liệu huấn luyện còn hạn chế về số lượng.

- <b>Minh họa</b>
![](images/minhhoa.png)


### Phân loại bài toán

Bài toán này, ta phải nhận hạng được hành động bạo lực, thông qua kỹ thuật trích xuất đặc trưng và phát hiện hành động bạo lực đó. Có thể nói, đây thuộc loại bài toán về <b>Object detection</b>. Bằng mô hình đã training, chúng ta có thể phân loại đâu là video có chứa hành động bạo lực, đâu là video bình thường và vị trí của chúng trong video.
<p align="center">
  <img width="460" height="300" src="https://github.com/nhavd/CS2225.CH1501/blob/master/Violence%20Detection/images/objecdetection.png">
</p>

## Phương pháp giải quyết bài toán

dscdsc
Sử dụng mô hình Deep Learning – Convolutional Neural Network (CNN) kết hợp phương pháp Long Short Term Memory (LSTM). Một mạng CNN đưa các input video (frame) và các output đặc trưng vào LSTM để học các đặc trưng global temporal, sau đó phân loại các đặc trưng bằng các mạng kết nối đầy đủ (fully connected layer). Network này không chỉ implement được bởi các pre-trained mode trong ImageNet database, mà nó rất linh hoạt để thực hiện trên các video có thời lượng bất định, và độ chính xác có thể lên đến 98,5% mặc dù xử lý hình ảnh theo thời gian thực.



## Vấn đề về dữ liệu

dscdsc
dsc
ds
c
sd

## Thực thi

dscdsc
dsc
ds
c
sd

## Kết quả

dscdsc
dsc
ds
c
sd

## Đánh giá

The proposed approach outperforms the state-of-the-art methods, while still processing the videos in real-time. The proposed model has the following advantages:

The ability to use the pre-trained model on ImageNet dataset.
The ability to learn the local motion features by examined the concatenated two frames using CNN.
The ability to learn the global temporal features by LSTM cell.
c
sd

Đồ án kết hợp giữa convloutional neural networks (Transfer learning) và long short term memory để  phân loại video thành hai loại chính 
* 0: No Violence 
* 1: Violence
sử dụng CNN-LSTM

Kiến trúc cụ thể

![](images/model.png)






```
pip install mxnet-cu101 # which should match your installed cuda version
```


*LResNet100E-IR* network trained on *MS1M-Arcface* dataset with ArcFace loss:

| Method  | LFW(%) | CFP-FP(%) | AgeDB-30(%) |  
| ------- | ------ | --------- | ----------- |  
|  Ours   | 99.80+ | 98.0+     | 98.20+      |   




## Datasets:

* [Hockey Fight Dataset](https://academictorrents.com/details/38d9ed996a5a75a039b84cf8a137be794e7cee89)

* [Movies Fight Dataset](https://academictorrents.com/details/70e0794e2292fc051a13f05ea6f5b6c16f3d3635)

* [Surveillance Cameras](https://github.com/sayibet/fight-detection-surv-dataset)
