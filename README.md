# loadJSONFromURL

## [참고자료 링크](https://min9nim.github.io/2018/10/json-server/)

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
