# 제품 매뉴얼 데이터 기반 QA 챗봇 서비스

## 프로젝트 소개
제품 매뉴얼 PDF 데이터를 수집하고 정제하여 대규모 QA 데이터셋을 구축하고 이를 바탕으로 RAG(Retrieval-Augmented Generation) 기반의 QA 챗봇 프로젝트
사용자의 질문을 분석하고, 제품 데이터베이스를 바탕으로 사용자가 찾고자하는 정보를 정확하고 신속하게 제공

## 사용법
1. 서비스 링크에 접속합니다
2. 하단에 있는 질문 입력 박스를 클릭하여 삼성 전자기기 제품에 대한 궁금한 점들을 입력합니다
3. 우측 하단 Send 버튼 좌측에 있는 선택창을 클릭하여 Assitant를 선택한 후 Send버튼을 클릭합니다
4. 챗봇이 질문을 분석하여 질문에 맞는 답변을 QA 데이터셋을 바탕으로 실시간으로 응답을 제공합니다

## 배포된 링크
QA 챗봇 서비스 링크  
https://d10ek5tvv5syc7.cloudfront.net/

# 로컬 실행 방법
## 1. 레포지토리 클론
git clone https://github.com/ssafy-12-data-3/project.git
## 2. 필수 환경 설정 파일 생성
프로젝트 실행에 필요한 환경 변수를 저장학 위해 아래 경로에 .env 파일을 생성

백엔드 환경 설정: src/backend/.env

프론트엔드 환경 설정: src/frontend/.env.development



백엔드 (src/backend/.env):

OPENAI_API_KEY= {https://platform.openai.com/api-keys 사이트에서 발급받은 API key} 

PINECONE_API_KEY= {https://www.pinecone.io/ 사이트에서 발급받은 API key} 

ASSISTANT_BOT_ID= {https://platform.openai.com/playground/assistants 사이트에서 학습시킨 Assistants의 id}

UPSTAGE_API_KEY= {https://she11.tistory.com/252 사이트 참고해서 받은 API key}

프로트앤드 (src/frontend/.env.development):

API_ENDPOINT=http://localhost:8000


## 3. 백앤드 의존성 설치 및 로컬에 서버 배포
src/backend/ 로 경로 이동후 아래 명령어 순서대로 실행

pip install -r requirements.txt
python app.py
로컬에 배포 후 http://localhost:8000/docs 경로로 접속해 잘 배포되었는지 확인

## 4. 프로트앤드 의존성 설치 및 로컬에 서버 배포
window 환경에서는 git bash에서 실행
parcel 설치 후 package.json에 정의된 모든 의존성 설치

npm install -g parcel
npm install
npm start
프론트 서버 로컬에 배포 후 배포된 서버에서 서비스 이용해보기

## 5. 서비스 확인인
http://localhost:1234/에 접속하여 QA 챗봇 이용하기

"삼성 키보드에서 예측 텍스트 및 자동 수정 기능을 사용하는 방법은 무엇인가요?"

"모바일 핫스팟에서 Wi-Fi 공유를 어떻게 활성화할 수 있나요?"

"갤럭시 A356B/DS에서 휴지통 기능을 사용하는 방법은 무엇인가요?"

"배경 이미지를 변경하려면 어떻게 해야 하나요?"

"Samsung Notes에서 노트를 정렬하는 방법은 무엇인가요?"
