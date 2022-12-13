# loadJSONFromURL

## [참고자료 링크](https://min9nim.github.io/2018/10/json-server/)

## json 서버 만들기
### 1. [nodejs.org](https://nodejs.org/ko/download/)에서 node를 다운로드 받아 설치
### 2. 프로젝트 폴더를 만들고 cmd를 열어 해당 폴더로 이동
### 3. npm init
```cmd
npm init 
```
### 4. json-server 설치
```cmd
npm install json-server --save-dev
```
### 5. /server.js작성
```javascript
const jsonServer = require('json-server')
const server = jsonServer.create()
const path = require('path')
const router = jsonServer.router(path.join(__dirname, 'db.json'))
const middlewares = jsonServer.defaults()

// Set default middlewares (logger, static, cors and no-cache)
server.use(middlewares)

// To handle POST, PUT and PATCH you need to use a body-parser
// You can use the one used by JSON Server
server.use(jsonServer.bodyParser)

server.use(router)

let port = 80;
server.listen(port, () => {
  console.log(`JSON Server is running, port(${port})`)
})
```
### 6. 데이터베이스로 이용할 /db.json 파일 생성
```cmd
{
  "posts": [
    { "id": 1, "title": "json-server", "author": "typicode" }
  ],
  "comments": [
    { "id": 1, "body": "some comment", "postId": 1 }
  ],
  "profile": { "name": "typicode" }
}
```
### 7. 서버 실행
```cmd
node server.js
```
### 8. 브라우저에서 접속(별도의 네트워크 세팅을 할 줄 모른다면 서버와 클라이언트는 같은 네트워크에 접속되어 있어야 접속이 가능함)
![json-server](https://user-images.githubusercontent.com/13882302/207355609-3b369a0c-8838-468e-8121-fe99b20d90a7.png)
![image](https://user-images.githubusercontent.com/13882302/207355742-af365e04-f523-4ae7-9226-c577d38689e0.png)


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
