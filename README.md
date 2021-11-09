# 안면인식 어플리케이션 개발 프로젝트
2021-Face-Detection-Recognition-Project

---

<br> 

## 프로젝트 구현 과정
1. 모델 분석 및 설계
2. 데이터 수집 및 전처리
3. Fine-tuning
4. 모델 테스트
5. 실시간 인식 테스트
6. 안드로이드 앱 포팅

<br> 

---

<br> 

1. 모델 분석 및 설계
- 논문 등 자료 조사를 통해 얼굴 인식에 대한 정보 수집

<br> 

2. 데이터 수집 및 전처리
- 자료 수집 
  - 눈, 코, 입이 제대로 나오지 않은 사진은 제외
  - 얼굴 가림(occlusion), 두 사람 이상 나온 사진 제외

<br> 

3. Fine-tuning
- [AI hub 한국인 얼굴 데이터](https://aihub.or.kr/aidata/73) 및 해외 유명인사 얼굴 사진으로 훈련

<br> 

4. 모델 테스트
- `inference.py`로 훈련된 모델을 테스트
- `hyper parameter`를 바꾸어가며 적절한 threshold, margin값 지정
- `test.py`에서 추론 테스트

<br> 


5. 실시간 인식 테스트
        OpenCV를 이용해 비디오 파일(eg. youtube video)을 테스트
        웹캠을 통한 실시간 얼굴 검출(detection) 및 인식(recognition) 테스트

<br> 


6. 안드로이드 앱 구현
- 사전 훈련된 모델을 `tensorflow-lite` 버전으로 전환
- 용량이 큰 문제로 축소버전인 `MobileFaceNet`의 `tensorflow-lite` 버전으로 구현함


<br> 


참고문헌
1) timesler - facenet-pytorch https://github.com/timesler/facenet-pytorch#pretrained-models
2) How to Train Your ResNet: The Jindo Dog (Thierry Laplanche) https://medium.com/analytics-vidhya/how-to-train-your-resnet-the-jindo-dog-50551117381d


도서
1) Practical Deep Learning for Cloud, Mobile, and Edge by Anirudh Koul, Siddha Ganju, and Meher Kasam (O’Reilly, 2019)
