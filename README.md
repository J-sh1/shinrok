
# 목차
  1. [서비스소개](#서비스소개)
  2. [주요기능](#주요기능)
  3. [시스템 아키텍처](#시스템-아키텍처)
  4. [서비스 흐름도](#서비스-흐름도)
  5. [화면구성(시연영상)](#화면구성시연영상)
  6. [팀원역할](#팀원역할)
  7. [초기 세팅](#초기-세팅)
  

## 서비스소개
초보 식집사들을 위한 식물관리 및 병충해 진단 서비스와 정보 공유 커뮤니티

## 주요기능
1. 사용자로부터 식물의 사진과 어떤 작물인지에 대한 정보를 라디오 버튼으로 입력을 받음
2. 사용자로부터 입력받은 식물의 사진과 어떤 작물인지에 대한 정보를 DB에 저장 및 모델로 전송
3. 모델이 입력받은 정보를 기반으로 식물의 병충해를 예측
4. 모델이 예측한 예측 결과를 DB에 저장 후 결과창을 띄워줌

## 시스템 아키텍처
![시스템 아키텍처](https://jsh-1.s3.ap-northeast-2.amazonaws.com/%ED%99%94%EB%A9%B4+%EC%BA%A1%EC%B2%98+2024-08-27+020009.png)

## 서비스 흐름도
![서비스 흐름도](https://jsh-1.s3.ap-northeast-2.amazonaws.com/%ED%99%94%EB%A9%B4+%EC%BA%A1%EC%B2%98+2024-08-27+020433.png)

## 화면구성(시연영상)
[시연 영상 보기](https://jsh-1.s3.ap-northeast-2.amazonaws.com/%EC%8B%9C%EC%97%B0%EC%98%81%EC%83%81.mp4)

## 팀원역할
![팀원역할](https://jsh-1.s3.ap-northeast-2.amazonaws.com/%ED%99%94%EB%A9%B4+%EC%BA%A1%EC%B2%98+2024-08-27+021438.png)

## 초기 세팅
### 1. Front 실행 환경 구성
#### 프로젝트 설정
1. VSCode에서 `ShinRok` 폴더를 엽니다.
2. 터미널에서 다음 명령어를 실행합니다.
    ```sh
    cd front
    npm install
    nodemon app.js
    ```
3. `.env` 파일을 생성하여 보안 관련 코드를 작성합니다.

### 2. Model 실행 환경구성
#### 프로젝트 설정
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
