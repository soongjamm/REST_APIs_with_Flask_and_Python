[Udemy - REST APIs with Flask and Python 강의 실습](https://www.udemy.com/course/rest-api-flask-and-python/)
==========================================================================================================

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
            - Resource class에 get, post.. 등의 method를 추가로 작성하더라도 해당 url에 대해서만 한번 코드를 작성하면 된다. 
    
    - Test-first API design
        - postman에서 /items (get)과 /item/<name> (get,post,delete,put)을 만들었는데 items와 item이 각각 리소스다. 즉 2개의 리소스가 있다.
        - 여기서 REST가 무엇인지 어렴풋이 알 수 있는데, 'post'를 사용함으로써 /item/create 라는 url을 만들 필요가 없어졌다.
