
# 📄프로젝트 정보

## 1. 프로젝트 소개
> 초보 식집사들을 위한 식물관리 및 **병충해 진단** 서비스와 정보 공유 커뮤니티🐛

## 2. 제작기간
> 24.07.22 ~ 24.08.01

## 3. 참여인원

> | 이름 | 역할 |
> | --- | --- |
> | 조승혁 | Back / Model |
> | 임정윤 | DB / Back |
> | 안수현 | Front / Design |
> | 고원희 | PM / Front |
> | 이정훈 | Back / Model |

![팀원역할](https://jsh-1.s3.ap-northeast-2.amazonaws.com/%ED%99%94%EB%A9%B4+%EC%BA%A1%EC%B2%98+2024-08-27+021438.png)

## 4. 내가 맡은 역할

- **모델 학습**
  - 학습에 사용한 데이터: [AI허브 - 시설 작물 질병 진단 이미지](https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=data&dataSetSn=153)
  - 데이터 전처리: 이미지 데이터와 라벨링 데이터 매핑
  - 모델 설계 및 학습

- **서버 및 환경 구축**
  - 모델 예측을 위한 로컬 환경 구축
  - Express, Flask 서버 구축 및 DB 연동
  - AWS S3 버킷을 활용한 이미지 저장 기능 구현

- **기능 구현**
  - 게시판 별 게시물 불러오기 및 상세보기 기능 구현
  - 게시글 수정 및 삭제 기능 구현
  - 비동기 댓글 기능 구현
  - 병충해 진단 페이지 제작 및 서버 간 통신 (Axios 활용)
  - 다이어리 불러오기 기능 구현
  - 마이페이지에서 병충해 진단결과 불러오기 및 상세페이지 기능 구현

- **테스트**
  - 단위 테스트 및 통합 테스트 진행

<br>

#  💻사용기술
## 1. Front
> ![HTML](https://img.shields.io/badge/HTML-239120?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-239120?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=JavaScript&logoColor=black)

## 2. Back
> ![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)

## 3. Model
> ![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![ResNet50](https://img.shields.io/badge/ResNet50-0078D4?style=for-the-badge&logo=ai&logoColor=white)

## 4. 기타
> ![Kakao](https://img.shields.io/badge/Kakao-FEE500?style=for-the-badge&logo=kakaotalk&logoColor=black)
![AWS S3](https://img.shields.io/badge/AWS%20S3-569A31?style=for-the-badge&logo=amazonaws&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

<br>

# 📋시스템아키텍처, 서비스흐름도, 시연영상

## 1. 시스템 아키텍처
<details>
<summary>시스템 아키텍처 펼쳐보기</summary>
  
![시스템 아키텍처](https://jsh-1.s3.ap-northeast-2.amazonaws.com/%ED%99%94%EB%A9%B4+%EC%BA%A1%EC%B2%98+2024-08-27+020009.png)

</details>

## 2. 서비스 흐름도
<details>
<summary>서비스 흐름도 펼쳐보기</summary>

![서비스 흐름도](https://jsh-1.s3.ap-northeast-2.amazonaws.com/%ED%99%94%EB%A9%B4+%EC%BA%A1%EC%B2%98+2024-08-27+020433.png)

</details>

## 3. 화면구성(시연 영상)
[클릭 시 영상이 재생됩니다.](https://jsh-1.s3.ap-northeast-2.amazonaws.com/%EC%8B%9C%EC%97%B0%EC%98%81%EC%83%81.mp4) <br>
소리가 클 수 있으니 주의 해주세요!!

# 💿핵심기능

## 1. 병충해 진단

1. **사용자 입력**
   - 사용자로부터 식물의 사진과 작물 종류를 라디오 버튼으로 입력받음.

2. **데이터 저장 및 전송**
   - 입력받은 식물의 사진과 작물 정보를 DB에 저장하고, 모델에 전송.

3. **병충해 예측**
   - 모델이 입력받은 정보를 기반으로 식물의 병충해를 예측.

4. **결과 저장 및 표시**
   - 모델의 예측 결과를 DB에 저장한 후, 결과창을 띄워 사용자에게 결과를 보여줌.

# 🗂️산출문서
[산출문서 바로가기](https://drive.google.com/drive/folders/1XQ3XyhBJjnDyQpw0U8z0sYyccLP9cGc6?usp=sharing)



# 🛠️초기 세팅
## 1. web 실행 환경 구성
### 프로젝트 설정
1. VSCode에서 `ShinRok` 폴더를 엽니다.
2. 터미널에서 다음 명령어를 실행합니다.
    ```sh
    cd web
    npm install
    nodemon app.js
    ```
3. `.env` 파일을 생성하여 보안 관련 코드를 작성합니다.

## 2. Model 실행 환경구성
### 프로젝트 설정
1. VSCode에서 `ShinRok` 폴더를 엽니다.
2. `Ctrl + Shift + P`를 누르고 `>Python: Select Interpreter`를 선택합니다.
3. 파이썬 버전을 선택합니다.
4. 터미널에서 다음 명령어를 실행합니다.
    ```sh
    cd model
    pip install -r requirements.txt
    python app.py
    ```
5. 만약 `pip install` 명령어가 작동하지 않는다면 다음을 수행합니다.
    - 윈도우 검색창에 시스템 환경 변수 편집을 입력하고 엽니다.
    - 고급 탭에서 환경 변수를 클릭합니다.
    - 시스템 변수 목록에서 Path를 찾아 클릭한 후 편집을 클릭합니다.
    - 새로 만들기를 클릭하고 다음 경로를 추가합니다.
        ```sh
        C:\Users\{사용자이름}\AppData\Local\Programs\Python\Python312\Scripts
        ```
    - VSCode를 재실행하고 `ShinRok` 폴더를 엽니다.
    - 터미널에서 해당 명령어를 다시 실행합니다.
        ```sh
        cd model
        pip install -r requirements.txt
        python app.py
        ```
    - 문제가 해결되지 않으면 컴퓨터를 재부팅합니다.
6. `.env` 파일을 생성하여 보안 관련 코드를 작성합니다.
7. [모델 다운로드](https://www.dropbox.com/scl/fi/37n03wq9icoxewm88gpyl/model_resnet50.pth?rlkey=oybb4n2mu9wrwkgw1o7o9n9hx&st=5loboqgt&dl=0) 링크를 클릭해서 모델을 설치합니다.
