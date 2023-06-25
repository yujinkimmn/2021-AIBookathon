<img width="691" alt="Screenshot 2023-06-25 at 2 28 06 PM" src="https://github.com/pastel-blue/2021_bookathon/assets/88418078/803c3114-2981-48b1-b1a4-d4ae6e008eb2"># 2021 제3회 AIxbookathon 대회

    전국 대학교 학부생을 대상으로 성균관대학교 학술정보관에서 주관한 대회이다.
    성균관대 데이터사이언스융합전공 학부생 3명이서 팀을 꾸려 대회에 참가, 장려상을 수상했다.

### 모델
마인즈랩에서 제공한 서버와 약 40GB 데이터가 사전 학습된 GPT-2 모델을 사용함.

### 크롤링 및 학습 데이터 (총 165.MB)
- 아이유, 악동뮤지션, 김광석 노래 가사
- 브런치 (유명 작가의 글, 여러 키워드를 설정하고 수집함)
- 한겨례 사설 "삶의 창"
- 이슬아 작가 수필
- <광화문> 연재소설
- <재미수필> 작가협회
- 글틴 문학광장

### 모델 학습 & Fine-tuning

    input token length를 확인하기 위해 브런치 데이터만을 가지고 학습을 시작했다. 텐서보드를 확인하며 파라미터를 조정하고, 중간에 잘 정제된 데이터를 추가로 학습해 learning rate decay 전략을 사용하였다.

<img width="691" alt="Screenshot 2023-06-25 at 2 27 03 PM" src="https://github.com/pastel-blue/2021_bookathon/assets/88418078/66d07f54-d30d-46eb-b2ae-c713627f99c2"><img width="691" alt="Screenshot 2023-06-25 at 2 27 21 PM" src="https://github.com/pastel-blue/2021_bookathon/assets/88418078/e88400a6-5ffd-4d72-8a2a-5bb18c5f1ba2">
<img width="691" alt="Screenshot 2023-06-25 at 2 27 47 PM" src="https://github.com/pastel-blue/2021_bookathon/assets/88418078/6987f2bd-0400-4205-8ed0-4543a88d5124"><img width="691" alt="Screenshot 2023-06-25 at 2 28 06 PM" src="https://github.com/pastel-blue/2021_bookathon/assets/88418078/bb61da80-89ee-4625-ba3c-8ebd1c405163">


