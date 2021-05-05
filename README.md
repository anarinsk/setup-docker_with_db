# Walk-through to create docker with db-postgresql 

## Trouble Shooting

### 권한 이슈 

#### 문제 

- WSL2 상에서 Windows 폴더와 postgres db의 저장 파일이 동기화되지 않는다. 
- 표면상으로는 권한 이슈로 뜬다. 

#### 해결책 1 

- docker 상에서 별도의 저장용 데이터 콘테이너를 만들어 여기 저장한다. 
- 이때 백업은 어떻게 할까? 

#### 더 살펴볼 것 

- adminer with docker 


### 연결 이슈 

#### 문제

두 도커가 연결되지 않는다. 

#### 해결책 1

`host='localhost'` -> `host='postgres'` 도커 콘테이너 이름으로 바꿔준다! 

#### Test code 

- 디비 연결 테스트 
```python 
!pip install psycopg2-binary
import psycopg2
import pandas as pd

db = psycopg2.connect(host='postgres', 
                     port=5432, 
                     user='root', 
                     password='1022', 
                     dbname='testdb')
```
#### 참고 

- 노트북에서 매직코멘트를 활용해 sql을 쓰는 방법 등을 소개 

https://medium.com/analytics-vidhya/postgresql-integration-with-jupyter-notebook-deb97579a38d

