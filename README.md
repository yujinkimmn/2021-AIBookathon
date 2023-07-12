# 2021 제3회 AIxbookathon 대회

<p align="center"> <img width="490" alt="image" src="https://github.com/yujinkimmn/2021-AIBookathon/assets/75295578/e7af9883-07fa-439f-b536-0ad8effd1086"> </p>


    전국 대학교 학부생을 대상으로 성균관대학교 학술정보관에서 주관한 대회이다.
    이번 대회 주제는 "함께" 이다.
    성균관대 데이터사이언스융합전공 학부생 3명이서 팀을 꾸려 대회에 참가, 장려상을 수상하였다.

### 모델
마인즈랩에서 제공한 서버와 약 40GB 데이터가 사전 학습된 GPT-2 모델을 사용함.
##
### 크롤링 및 학습 데이터 (총 165.MB)
- 아이유, 악동뮤지션, 김광석 노래 가사
- 브런치 (유명 작가의 글, 여러 키워드를 설정하고 수집함)
- 한겨례 사설 "삶의 창"
- 이슬아 작가 수필
- <광화문> 연재소설
- <재미수필> 작가협회
- 글틴 문학광장
##
### 모델 학습 & Fine-tuning

    input token length를 확인하기 위해 브런치 데이터만을 가지고 학습을 시작하였다. 
    텐서보드를 확인하며 파라미터를 조정하고, 중간에 잘 정제된 데이터를 추가로 학습해 learning rate decay 전략을 사용하였다.

<img width="691" alt="Screenshot 2023-06-25 at 2 27 03 PM" src="https://github.com/pastel-blue/2021_bookathon/assets/88418078/66d07f54-d30d-46eb-b2ae-c713627f99c2"><img width="691" alt="Screenshot 2023-06-25 at 2 27 21 PM" src="https://github.com/pastel-blue/2021_bookathon/assets/88418078/e88400a6-5ffd-4d72-8a2a-5bb18c5f1ba2">
<img width="691" alt="Screenshot 2023-06-25 at 2 27 47 PM" src="https://github.com/pastel-blue/2021_bookathon/assets/88418078/6987f2bd-0400-4205-8ed0-4543a88d5124"><img width="691" alt="Screenshot 2023-06-25 at 2 28 06 PM" src="https://github.com/pastel-blue/2021_bookathon/assets/88418078/bb61da80-89ee-4625-ba3c-8ebd1c405163">
##
### Customizing

    기존에 마인즈랩으로부터 제공받은 코드에서
    더 나은 학습 성능을 위해 Feeder를,
    더 나은 문장 생성을 위해 Sampler를 수정하였다.

    feeder는 training 시에 입력할 데이터를 추출하는 방법을 조정하는 모듈이고, 
    sampler는 inference 시에 샘플링할 token distribution을 조정하는 모듈로 top_k와 top_p 방식을 지원한다.

    우리팀은 학습할 때 토픽 모델링을 적용하기 위한 함수를 feeder에 추가하고, top_k와 top_p 방식 각각의 단점을 보완하기 위한 코드를 sampler에 추가하였다. 
    구체적으로, top_p inferring 결과 변수를 생성해 top_p에서 선택된 개수를 확인하고, 해당 개수가 top_k의 k개보다 작거나 같으면 top_p 결과를 리턴하고, 
    이보다 크면 결과값에 top_k inferring 알고리즘을 적용하게 된다.
##
### 결과물
<img width="691" alt="Screenshot 2023-06-25 at 2 37 48 PM" src="https://github.com/pastel-blue/2021_bookathon/assets/88418078/f5ea732b-257e-4d9f-98d9-f6d2cfa9f130">

최종 제출물은 문서에서 확인할 수 있다.
