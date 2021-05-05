# Walk-through to create docker with db-postgresql 

## Trouble Shooting

### 권한 이슈 

### 연결 이슈 

- 문제: 두 도커가 연결되지 않는다. 

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

- 해결책 

`host='localhost'` -> `host='postgres'` 도커 콘테이너 이름으로 바꿔준다! 

## Jupyter에서 SQL 쓰기 

https://medium.com/analytics-vidhya/postgresql-integration-with-jupyter-notebook-deb97579a38d

