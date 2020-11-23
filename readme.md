[Udemy - REST APIs with Flask and Python 강의 실습](https://www.udemy.com/course/rest-api-flask-and-python/)

#### 사용된 도구
Python 3.9
Flask-RESTful

#### 실행하기
- source venv/bin/activate
- python app.py (code 디렉토리에서 실행)

#### 메모
- Flask-RESTful
    - Resource
        - API가 나타내는 것. 예를 들어 students를 다루는 API에서 create students, return students 등등 student가 resource가 된다.DB테이블과 맵핑된다.
        - DB 테이블과 맵핑된다.
        - 클래스여야 한다.
    - Api
        - 아주 쉽게 Resource를 add 할 수 있게 도와준다.
        - 데코레이터로 endpoint를 설정하지 않고 add_resource 메소드를 사용하여 Student에 접근한다.
