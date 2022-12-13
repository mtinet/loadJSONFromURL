# loadJSONFromURL

## [참고자료 링크](https://min9nim.github.io/2018/10/json-server/)

## json 서버 만들기
### 1. [nodejs.org](https://nodejs.org/ko/download/)에서 node를 다운로드 받아 설치
### 2. 프로젝트 폴더를 만들고 cmd를 열어 해당 폴더로 이동
### 3. npm init
```cmd
npm init 
```

## pothon으로 위 자료를 참고하여 만든 json서버에서 json을 불러오는 방법
### 1. requests 라이브러리 설치
```python
pip install requests
```

### 2. test.py
```python
import requests

url = "http://localhost/posts"
data = requests.get(url).json()
print(data)
```
