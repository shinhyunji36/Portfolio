# 기업 과제 3: Semantic Textual Similarity (STS)

3팀: 김소연, 박수웅, 신현지, 이준혁, 최소윤

## 목표
두 한국어 문장 간의 의미적 유사도 추론

## 학습 데이터
KLUE(Korean Language Understanding Evaluation) 의 STS Dataset 
(https://klue-benchmark.com/)

## Demo: FastAPI의 Swagger UI를 통해 구현 
### 사용한 모델

KLUE/RoBERTa-base

### 실행 방법
1. 다음의 링크에서 모델의 checkpoint 폴더(`Team3_best_checkpoint`)를 압축하여 다운로드 받는다:<br/> https://drive.google.com/drive/folders/1-5pjn_091zw-UfVU0eD_QEdtO3APCFN1?usp=sharing
2. Working Directory 에 (1) 압축을 푼 checkpoint 폴더와 (2) `main.py`,  (3) `requirement.txt` 파일을 위치시킨다. 
3. 터미널에서 다음의 코드를 실행하여 필요한 패키지들을 설치한다.: ```pip install -r requirements.txt```
4. 다음의 코드를 통해 서비스를 호출한다: ```uvicorn main:app --reload```
5. 터미널에 생성된 주소(e.g. `http://127.0.0.1:8000`)를 `CTRL+C` 를 누른채 클릭한다.
6. 새로운 웹페이지가 로드되면 url 을 기존 주소 (e.g. `127.0.0.1:8000`) 에 `/docs` 를 붙인 뒤 (e.g.`127.0.0.1:8000/docs`), 엔터를 클릭해 Swagger UI로 이동한다.
7. 초록색의 `POST` box 를 클릭한 뒤 우측의 `Try it out` 버튼을 누른다.
8. 다음과 같이 `sentence1`, `sentence 2` 에 유사도를 비교하고자 하는 문장을 입력한 뒤 <br/> 아래의 파란색 `Execute` 버튼을 클릭한다. 
     
  ![api1](https://user-images.githubusercontent.com/68551097/159854424-4477d90e-c99b-452e-88a4-ae8366083eb8.png)
  
9. 스크롤을 내려 초록색 body 의 `Responses - Server response` section 에서 두 문장의 유사도를 확인할 수 있다. 

![api2](https://user-images.githubusercontent.com/68551097/159854837-d661820f-4534-423a-87f0-8fbbf4aaebe5.png)
