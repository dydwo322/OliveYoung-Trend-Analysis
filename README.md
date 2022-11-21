# Text-Mining Project(OliveYoung-Trend-Analysis)

<img width="500" alt="OliveYoung" src="https://user-images.githubusercontent.com/79880476/203081488-d2794fad-7fd3-4b0a-b3c3-0cfa46ebdf51.jpg">

### ○ 프로젝트 주제 
올리브영의 고객 리뷰 데이터와 화장품이 가진 성분들을 이용해 트렌드와 관련된 요소들을 분석해 보고 소비자 성향을 분석

### ○ 프로젝트 기간
22.08.08 ~ 22.08.19

### ○ 프로젝트 분석 목표

<div><img width="500" height="150px" alt="crawling" src="https://user-images.githubusercontent.com/79880476/203086943-b69dde05-c282-441d-aadf-669bd20959df.jpg"><p>- 크롤링을 통해 활용할 수 있는 데이터 파악</p></div>

<div><img width="500" height="150px" alt="ewa" src="https://user-images.githubusercontent.com/79880476/203086934-481ca132-a434-43dc-a464-79a3f2eece89.jpg"><p>- 제품에 들어간 성분의 등급 점수와 리뷰 점수와의 상관관계 분석</p></div>

<div><img width="500" height="150px" alt="keyword" src="https://user-images.githubusercontent.com/79880476/203089489-1cadf244-8dd0-44a5-b449-540cce9b6632.jpg"><p>- 상품 설명에서 어필 하고 있는 키워드와 리뷰에서 해당 키워드가 일치하는지 분석</p></div>

---
# 가. 데이터 

---

# 나. 전처리

---

# 다. 데이터 분석방법
 출처 : 국립국어원, 2022 인공지능 언어 능력 평가 말뭉치: ABSA 

    {"id": "nikluge-sa-2022-train-00001", "sentence_form": "둘쨋날은 미친듯이 밟아봤더니 기어가 헛돌면서 틱틱 소리가 나서 경악.", "annotation": [["본품#품질", ["기어", 16, 18], "negative"]]}
    {"id": "nikluge-sa-2022-train-00002", "sentence_form": "이거 뭐 삐꾸를 준 거 아냐 불안하고, 거금 투자한 게 왜 이래.. 싶어서 정이 확 떨어졌는데 산 곳 가져가서 확인하니 기어 텐션 문제라고 고장 아니래.", "annotation": [["본품#품질", ["기어 텐션", 67, 72], "negative"]]}
    {"id": "nikluge-sa-2022-train-00003", "sentence_form": "간사하게도 그 이후에는 라이딩이 아주 즐거워져서 만족스럽게 탔다.", "annotation": [["제품 전체#일반", [null, 0, 0], "positive"]]}

---

# 라. 이슈 및 해결

#### 1. Augmentation - RI(Random Insertion): 감탄사와 의성어를 문장 내에 추가하는 방식

       
    ex) 나는 자전거 타는 것을 좋아한다. -> 와! 나는 자전거 타는 것을 좋아한다.
   
        
#### 2. Back-Translation


    원본) 나는 자전거 타는 것을 좋아한다. 

    한국어 -> 프랑스어) J'aime faire du vélo. 

    프랑스어 -> 한국어) 저는 자전거 타는 것을 좋아해요.

   위의 예와 같이 특정 문장을 다른 언어로 번역한 후 다시 한국어로 번역하여 의미는 같지만 형태가 다른 문장을 생성하는 방식
    
#### 3. 외부 API 활용
 
   크롤링한 데이터(출처: 네이버쇼핑, 올리브영)에 대해 NAVER CLOVA Sentiment API를 이용하여 Label을 'neutral'과 'negative'를 부여하는 방식
    
---
# 마. 분석 

#### 1. Augmentation - RI(Random Insertion): 감탄사와 의성어를 문장 내에 추가하는 방식

       
    ex) 나는 자전거 타는 것을 좋아한다. -> 와! 나는 자전거 타는 것을 좋아한다.
   
        
#### 2. Back-Translation


    원본) 나는 자전거 타는 것을 좋아한다. 

    한국어 -> 프랑스어) J'aime faire du vélo. 

    프랑스어 -> 한국어) 저는 자전거 타는 것을 좋아해요.

   위의 예와 같이 특정 문장을 다른 언어로 번역한 후 다시 한국어로 번역하여 의미는 같지만 형태가 다른 문장을 생성하는 방식
    
#### 3. 외부 API 활용
 
   크롤링한 데이터(출처: 네이버쇼핑, 올리브영)에 대해 NAVER CLOVA Sentiment API를 이용하여 Label을 'neutral'과 'negative'를 부여하는 방식
---
# 바. 사용 코드 
<table>
    <thead>
        <tr>
            <th>목록</th>
            <th>파일명</th>
            <th>설명</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=3>Data 만들기</td>
            <td>
                <a href="https://github.com/HappyBusDay/Korean_ABSA/blob/main/code/Data_Augmentation.ipynb">Data_Augmentation.ipynb</a>
            </td>
            <td> Random_Insertion, Random_Swap, Random_Deletion Code</td>
        </tr>
        <tr>
            <td>
                <a href="https://github.com/HappyBusDay/Korean_ABSA/blob/main/code/Back_Translation.ipynb">Back_Translation.ipynb</a>                
            <td> Back_Translation Code</td>
        </tr>
        <tr>
            <td>
                <a href="https://github.com/HappyBusDay/Korean_ABSA/blob/main/code/MakeData_with_API.ipynb">MakeData_with_API.ipynb</a>     
            <td> Naver Open API를 이용하여 데이터의 라벨을 달아주는 Code </td>
        <tr>
            <td>Model Training</td>
            <td>
                <a href="https://github.com/HappyBusDay/Korean_ABSA/blob/main/code/train.ipynb">train.ipynb</a>     
            <td> Model과 Data를 불러와 학습시키는 Code </td>
        </tr>
        <tr>
            <td>Prediction</td>
            <td>
                <a href="https://github.com/HappyBusDay/Korean_ABSA/blob/main/code/test.ipynb">test.ipynb</a>     
            <td> 학습 시켰던 Model의 Weights를 불러와서 새로운 데이터의 결과값을 예측하는 Code </td>
        </tr>        
        <tr>
            <td rowspan=2>Model Ensemble</td>       
            <td>
                <a href="https://github.com/HappyBusDay/Korean_ABSA/blob/main/code/Manual_Ensemble.ipynb">Manual_Ensemble.ipynb</a>
            <td> Prediction의 결과(jsonl파일)를 불러와서 Hard Voting하는 Code</td>
        </tr>
        <tr>
            <td>
                <a href="https://github.com/HappyBusDay/Korean_ABSA/blob/main/code/Auto_Ensemble.ipynb">Auto_Ensemble.ipynb</a>
            <td>다양한 조합의 결과를 도출하는 Ensemble code</td>
        </tr>
        <tr>
            <td>구현코드</td>
            <td>
                <a href="https://github.com/HappyBusDay/Korean_ABSA/blob/main/code/test_and_ensemble_realizing.ipynb">test_and_ensemble_realizing.ipynb</a>
            <td>최종 점수 재현 및 검증을 위한 코드</td>
        </tr>        
    </tbody>
</table>


---

###  ○ 역할
- 이재엽 : 데이터 크롤링(리뷰) & 데이터 등급점수와 리뷰점수간 상관관계 분석 
- 김용재 : 데이터 크롤링(화장품의 성분표) & 데이터 전처리(성분표)
- 정효제 : 데이터 크롤링(광고 키워드) & 데이터 전처리(성분표) 
- 한서연 : 데이터 크롤링(리뷰어의 선택 키워드) & 데이터 키워드 간 상관관계 분석
- 이정아 : 데이터 크롤링(화장품 성분 등급) & 데이터 등급점수와 리뷰점수간 상관관계 분석 
- 전은성 : 데이터 크롤링(리뷰어의 선택 키워드) & 데이터 키워드 간 상관관계 분석
