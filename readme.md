[Udemy - REST APIs with Flask and Python 강의 실습](https://www.udemy.com/course/rest-api-flask-and-python/)
==========================================================================================================

### 사용된 도구
Python 3.9
Flask-RESTful

### 실행하기
- source venv/bin/activate
- python app.py (code 디렉토리에서 실행)

### 메모
- __Flask-RESTful__
    - Resource
        - API가 나타내는 것. 예를 들어 students를 다루는 API에서 create students, return students 등등 student가 resource가 된다.DB테이블과 맵핑된다.
        - DB 테이블과 맵핑된다.
        - 클래스여야 한다.
    - Api
        - 아주 쉽게 Resource를 add 할 수 있게 도와준다.
        - 데코레이터로 endpoint를 설정하지 않고 add_resource 메소드를 사용하여 Student에 접근한다.
            - Resource class에 get, post.. 등의 method를 추가로 작성하더라도 해당 url에 대해서만 한번 코드를 작성하면 된다. 
    
- __Test-first API design__
    - postman에서 /items (get)과 /item/<name> (get,post,delete,put)을 만들었는데 items와 item이 각각 리소스다. 즉 2개의 리소스가 있다.
    - 여기서 REST가 무엇인지 어렴풋이 알 수 있는데, 'post'를 사용함으로써 /item/create 라는 url을 만들 필요가 없어졌다.

- __Flask-JWT (JSON Web Token)__
    - 데이터를 인코딩 & 디코딩하여 인증과정을 거치는데 이 과정을 쉽게 도와주는 라이브러리이다.
    - JWT setup을 한다. JWT()는 새로운 endpoint (/auth)를 만든다.
        - /auth를 호출하면 JWT가 username, password를 받고 authenticate 함수로 전달한다. 매칭되면 user를 리턴하고 identity 함수를 실행한다. 그리고 JW token을 리턴한다.
        - 여기서 JW token은 아무 역할을 하지 않고 다음에 사용할 decorator로 전달한다.
    - @jwt_required() 데코레이터를 사용함으로써 메소드 시작 전에 사용자 인증을 한다.
        - JW token을 보내주어야 JWT-Flask에서 '유저가 로그인 해있다'고 알 수 있다. 
            - headers에 _key: Authorization, value: JWT {JWT 토큰}_ 을 포함시켜주어야 인증된다. (로그인)
            - 위 과정을 거치지 않으면 'Authorization Required' 라는 에러 메세지를 받게 된다.
        - 데코레이터가 호출되면 JW token을 같이 보낸다. 이 때 JWT가 하는 일은 identity를 호출하고 user ID를 얻기 위하여 JW token을 전달, JW token이 나타내는 유저를 리턴받는다.

- __etc__
     next() : filter()로 특정 아이템을 get하면 하나의 값만이 매칭될 것을 알고 있다. next()로 감싸주면 매칭되는 첫번째 객체를 가져온다. 매칭되는 값이 없으면 에러가 발생하므로 두번째 인자로 None을 준다. (default value가 됌)