# NHẬN DẠNG HÀNH ĐỘNG BẠO LỰC QUA VIDEO 
GROUP N009: [Pham Duc Duy](duypd.13@grad.uit.edu.vn ) - [Dong Dang Khoa](khoadd.14@grad.uit.edu.vn) - [Vo Dinh Nha](nhavd.14@grad.uit.edu.vn)

## License [![GitHub license](https://img.shields.io/github/license/Naereen/StrapDown.js.svg)](https://github.com/Naereen/StrapDown.js/blob/master/LICENSE)


## Violence Detection [![made-with-python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg)](https://www.python.org/) [![Open In Collab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com)
Là mục tiêu đề tài mà nhóm đã thảo luận và đưa ra ý kiến thống nhất

Để thực hiện và hoàn thành project, nhóm N009 đã lựa chọn phương pháp nhận diện hành động bạo lực bằng sự kết hợp giữa Convolution Neural Networks và Long Short Term Memory.

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
*[Mô tả bài toán](#mô-tả-bài-toán)*

*- [Giới thiệu](#giới-thiệu)*

*- [Phân loại bài toán](#phân-loại-bài-toán)*

*[Phương pháp giải quyết bài toán](#phương-pháp-giải-quyết-bài-toán)*

*[Vấn đề về dữ liệu](#vấn-đề-về-dữ-liệu)*

*[Thực thi](#thực-thi)*

*[Kết quả](#kết-quả)*

*[Đánh giá](#đánh-giá)*
*********************************************************************************************

## Mô tả bài toán

dscdsc
dsc
ds
c
sd

### Giới thiệu

dscdsc
dsc
ds
c
sd

### Phân loại bài toán

dscdsc
dsc
ds
c
sd

## Phương pháp giải quyết bài toán

dscdsc
dsc
ds
c
sd


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

dscdsc
dsc
ds
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




## Datasets của đồ án tham khảo tại:

* [Hockey Fight Dataset](https://academictorrents.com/details/38d9ed996a5a75a039b84cf8a137be794e7cee89)

* [Movies Fight Dataset](https://academictorrents.com/details/70e0794e2292fc051a13f05ea6f5b6c16f3d3635)

* [Surveillance Cameras](https://github.com/sayibet/fight-detection-surv-dataset)
