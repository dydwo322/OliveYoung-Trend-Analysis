# Text-Mining Project(OliveYoung-Trend-Analysis)

<img width="500" alt="OliveYoung" src="https://user-images.githubusercontent.com/79880476/203081488-d2794fad-7fd3-4b0a-b3c3-0cfa46ebdf51.jpg">

### ○ 프로젝트 주제 
올리브영의 고객 리뷰 데이터와 화장품이 가진 성분들을 이용해 트렌드와 관련된 요소들을 분석해 보고 소비자 성향을 분석

### ○ 프로젝트 기간
22.08.08 ~ 22.08.19

### ○ 프로젝트 목표

<table style="text-align: center;">
  <tr align=center>
    <td><img src="https://user-images.githubusercontent.com/79880476/203086943-b69dde05-c282-441d-aadf-669bd20959df.jpg" ></td>
  </tr>
  <tr align=center><td>- 크롤링을 통해 활용할 수 있는 데이터 파악</td></tr>
  <tr align=center>
    <td><img src="https://user-images.githubusercontent.com/79880476/203086934-481ca132-a434-43dc-a464-79a3f2eece89.jpg"></td>
  </tr>
  <tr align=center><td>- 제품에 들어간 성분의 등급 점수와 리뷰 점수와의 상관관계 분석</td></tr>
  <tr align=center>
    <td><img src="https://user-images.githubusercontent.com/79880476/203089489-1cadf244-8dd0-44a5-b449-540cce9b6632.jpg"></td>
  </tr>
  <tr align=center><td>- 상품 설명에서 어필 하고 있는 키워드와 리뷰에서 해당 키워드가 일치하는지 분석</td></tr>
</table>

---

# 0. 목차
<table>
    <thead>
        <tr align=center>
            <th>번호</th>
            <th>목차</th>   
        </tr>
    </thead>
    <tbody>
        <tr align=center>
            <td>1</td>
            <td><a href="#1">데이터 수집</a></td>
        </tr>
        <tr align=center>
            <td>2</td>
            <td><a href="#2">전처리</a></td>
        </tr>
        <tr align=center>
            <td>3</td>
            <td><a href="#3">이슈</a></td>
        </tr>
        <tr align=center>
            <td>4</td>
            <td><a href="#4">해결</a></td>
        </tr>
        <tr align=center>
            <td>5</td>
            <td><a href="#5">분석</a></td>
        </tr>
        <tr align=center>
            <td>6</td>
            <td><a href="#6">결론</a></td>
        </tr>
        <tr align=center>
            <td>7</td>
            <td><a href="#7">사용 코드</a></td>
        </tr>
        <tr align=center>
            <td>8</td>
            <td><a href="#8">피드백</a></td>
        </tr>
        <tr align=center>
            <td>9</td>
            <td><a href="#9">멤버 & 역할</a></td>
        </tr>  
     </tbody>
</table>
<br>
<br>

---
# 1. <a name="1">데이터 수집</a>
### 1. 올리브영 스킨/로션 화장품 성분표, 리뷰 크롤링
### 2.  리뷰어들의 세부 선택정보 크롤링
<br>
<br>

---
# 2. <a name="2">전처리</a>
### 1. 화장품의 성분표, 리뷰  전처리
### 2. Customized KoNLPy 라이브러리 활용해 화장품도메인  전처리
### 3. COOS를 이용한 화장품 성분별 등급 변환해주는 전처리
<br>
<br>

---
# 3. <a name="3">이슈</a>
### 1. 리뷰의 개수가 적은 제품, 같은 제품이지만 다른 상품으로 나오는 제품들, 제품당 크롤링 가능 개수 1000개 제한
<div><img width=950 height=200px src="https://user-images.githubusercontent.com/79880476/203359679-83ce4b32-9c73-4ef8-8dc2-8adda87fd33a.jpg"></div>

### 2. 성분표 제품별로 형식이 규격 없이 제각기로 표시됨
<div><img width=750 height=120px src="https://user-images.githubusercontent.com/79880476/203354047-174f18ee-a256-44aa-89c4-572d000ae7d4.jpg"></div>

### 3. 화장품 도메인에서만 사용하는 단어들이 토큰화X
<div><img width=750 height=120px src="https://user-images.githubusercontent.com/79880476/203356326-80c0c8ca-dc19-4dad-97dc-5025baf2cf72.jpg"></div>

### 4. 리뷰의 라벨링 & 긍부정 사전의 한계
<div><img width=750 height=150px src="https://user-images.githubusercontent.com/79880476/203354173-00230ec6-627c-4d85-acd2-59ed5764d351.jpg"></div>
<br>
<br>

---
# 4. <a name="4">해결</a>
### 1. 리뷰 개수 부족 & 중복 상품 제거 → 83개의 제품(제품당 댓글 개수는 충분하다고 판단)<br>
### 2. 성분표 제품별로 형식을 동일하게 정규표현식을 이용하여 정형화 작업
<div><img width=750 height=150px src="https://user-images.githubusercontent.com/79880476/203354045-5c64cbf4-0a61-4c62-938d-7552b9ff395d.jpg"></div>

### 3. Customized KoNLPy 라이브러리 활용하여 화장품 도메인 단어(닦토,흡토) 토큰화
<div><img width=950 height=450px src="https://user-images.githubusercontent.com/79880476/203356233-b6a8a8d7-a1b3-49c9-815f-1057df9383f0.jpg"></div>

### 4. 리뷰의 라벨링을 새로운 조건 및 정교화 작업을 통해 잘못 분류 되는 비중을 낮춤<br>
<br>
<br>

---
# 5. <a name="5">분석 </a>
### 1. 전체 리뷰의 내용을 LDA 토픽 모델링하여 '보습,진정,자극'의 3가지 카테고리로 분류 되었다.
<table>
  <tr align=center>
    <td><img src="https://user-images.githubusercontent.com/79880476/203334695-814dd302-4b38-4e94-9074-498f77e7481b.jpg"/>- LDA 토픽 모델링 전체 키워드</td><td><img  src="https://user-images.githubusercontent.com/79880476/203334717-d5722778-0356-4942-94dd-55fbbbb7f81a.jpg"/> - LDA 토픽 모델링 '진정'</td>
  </tr>
  <tr align=center>
    <td><img src="https://user-images.githubusercontent.com/79880476/203334744-42125897-ddec-4615-8892-2474f44d7300.jpg"/>- LDA 토픽 모델링 '자극'</td><td><img  src="https://user-images.githubusercontent.com/79880476/203334761-c921fe16-655c-413e-91f0-722e6d0f200c.jpg"/>- LDA 토픽 모델링 '보습'</td>
  </tr>
</table>

### 2. 제품 설명 강조 키워드 '보습,진정,자극'의 빈도를 수치화하여, 광고 키워드와 비교하였는데 83개 제품 중 14개만 일치하였다.
<table>
  <tr>
    <td><img src="https://user-images.githubusercontent.com/79880476/203334488-52d14bed-14c8-441a-8964-8b37a5aca6f1.jpg"></td>
  </tr>
  <tr align=center><td> -광고 키워드와 제품 키워드 비교</td></tr>
</table>

### 3. 성분 등급 점수 & 댓글 평가 지수 상관 관계 분석(긍정 - 하강그래프 / 부정 - 상승그래프가 이상적), 잘 나오지 않았다.

<table>
  <tr >
    <td><img src="https://user-images.githubusercontent.com/79880476/203342856-5e07e51c-10c1-4fae-8453-adef65f92d9b.jpg"></td>
  </tr>
  <tr align=center><td>- 전체 제품의 성분 score값과 긍부정 리뷰 비율의 그래프</td></tr>
</table>
<br>
<br>

---
# 6. <a name="6">결론</a>
<table>
  <tr >
    <td><img src="https://user-images.githubusercontent.com/79880476/203334516-b5bd2da3-e1b7-4946-ba8f-080848e02ccd.jpg"></td>
  </tr>
  <tr align=center><td>- 제품 키워드 이용한 키워드 분포도</td></tr>
</table>
  
### ∴ 제품 키워드 실제 효능과 무관하지만, 소비자에게 사용자(리뷰어)들이 평가한 효능 수치화 해서 정보 제공 목적으로 활용 가능하다고 판단하였습니다.<br>
<table>
  <tr >
    <td><img src="https://user-images.githubusercontent.com/79880476/203342847-cf1713b7-a786-44e1-8e07-13bed3558287.jpg"></td>
  </tr>
  <tr align=center><td>- 제품 성분등급 & 제품의 긍정 리뷰 지수 간의 상관관계 그래프</td></tr>
</table>

### ∴ 약간의 관계성이 있어 보이지만, 표본 데이터 83개 & 긍정 리뷰 비중이 95%정도 이기 때문에 연관성을 분석하기에 한계가 있고, 좀 더 정확한 분석을 하기위해서 데이터가 더 필요하다고 판단하였습니다.<br>
<br>
<br>

---
# 7. <a name="7">사용 코드</a>
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
            <td>올리브영 크롤링 코드</td>
            <td><a href = "https://github.com/dydwo322/OliveYoung-Trend-Analysis/blob/main/OliveYoung_Crawling.ipynb">OliveYoung_Crawling.ipynb</a></td>
            <td> 올리브영 제품의 리뷰, 성분표 크롤링 코드입니다.</td>
        </tr>
        <tr>
            <td>올리브영 전처리 코드</td>
            <td><a href = "https://github.com/dydwo322/OliveYoung-Trend-Analysis/blob/main/OliveYoung_Data_Preprocessing.ipynb">OliveYoung_Data_Preprocessing.ipynb</a></td>
            <td> 올리브영 제품의 리뷰, 성분표, 토큰화 전처리 코드입니다.</td>
        <tr>
            <td>올리브영 성분등급 변환 코드</td>
            <td><a href = "https://github.com/dydwo322/OliveYoung-Trend-Analysis/blob/main/OliveYoung_EWG_HazardScore_Change.ipynb">OliveYoung_EWG_HazardScore_Change.ipynb</a></td>
            <td> 올리브영 제품 성분들을 EWG성분등급으로 변환해 등급을 정해주는 코드입니다.</td>
        </tr>
        <tr>
            <td>올리브영 데이터 분석 코드</td>
            <td><a href = "https://github.com/dydwo322/OliveYoung-Trend-Analysis/blob/main/OliveYoung_LDA&Sentiment_analysis.ipynb">OliveYoung_LDA&Sentiment_analysis.ipynb</a></td>
            <td> 올리브영 리뷰를 통해 감성분석 & 키워드를 도출해 분석을 하는 코드입니다.</td>
        </tr>        
        <tr>
            <td>올리브영 광고키워드,리뷰키워드 비교 코드</td>
            <td><a href = "https://github.com/dydwo322/OliveYoung-Trend-Analysis/blob/main/OliveYoung_AD_Keyword.ipynb">OliveYoung_AD_Keyword.ipynb</a></td>
            <td> 올리브영 리뷰키워드와 제품키워드를 비교해 분석하는 코드입니다.</td>
        </tr>
        <tr>
            <td>올리브영 시각화 자료 코드</td>
            <td><a href = "https://github.com/dydwo322/OliveYoung-Trend-Analysis/blob/main/OliveYoung_Data_Visualization.ipynb">OliveYoung_Data_Visualization.ipynb</a></td>
            <td> 올리브영 리뷰&키워드 비교분석을 하며 시각화에 사용했던 코드 모음입니다.</td>
        </tr>    
    </tbody>
</table>
<br>
<br>

---
# 8. <a name="8">피드백</a>
- 성분의 성분별 등급을 스코어화 하는데 그것을 가지고 전체 스코어를 평균값을 구하고, 그것을 기준으로 비교 할 수 있는 지표(분산,평균치를 기준으로 4분위를 표시 etc..)을 구해서 추가해주면 좀 더 좋을 거 같다.
- 긍정리뷰의 비율과 성분등급의 minmaxscaled를 그린 그래프를 긍정비율의 상º하위 20%의 평균을 구해서 비교해봐라.
- 성분의 성분별 등급을 스코어화 하는데 과정을 좀 더  추가 해줬으면 좋겠다. 과정을 모르는 학생분들은 알기 쉽지 않다.
- 마지막 그래프에서 기존 앞에 보여준 스코어랑 달리 minmaxscaled로 수치로 바꾸는 과정 왜 선택해서 바꿔서 그래프를 그렸는지 이유랑 이런것을 보여주는게 필요할 거 같다.
- 토큰화 시, 안걸러지는 도메인 용어를 용어사전으로 만들어서 커스텀마이징을 이용한 것은 잘했다.
- 주제가 되게 괜찮았다. 또한 여러가지 성분 등급표, 광고 키워드 등 여러가지 활용할 수있는 자료들이 많았던 조였고, 나중에 이를 통해서 성분쪽으로 관련지어 진행해서 하면 괜찮을 것 같다.
<br>
<br>

---
#  9. <a name="9">멤버 & 역할</a>
- 이재엽(조장) : 데이터 크롤링(리뷰) & 데이터 등급점수와 리뷰점수간 상관관계 분석 
- 김용재 : 데이터 크롤링(화장품의 성분표) & 데이터 전처리(성분표)
- 정효제 : 데이터 크롤링(광고 키워드) & 데이터 전처리(성분표) 
- 한서연 : 데이터 크롤링(리뷰어의 선택 키워드) & 데이터 키워드 간 상관관계 분석
- 이정아 : 데이터 크롤링(화장품 성분 등급) & 데이터 등급점수와 리뷰점수간 상관관계 분석 
- 전은성 : 데이터 크롤링(리뷰어의 선택 키워드) & 데이터 키워드 간 상관관계 분석
