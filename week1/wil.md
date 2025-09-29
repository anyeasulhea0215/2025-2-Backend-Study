# 1. 웹

웹: 인터넷 위에서 동작하는 다양한 서비스 중 하나.
인터넷에 연결괸 전 세계 사용자들이 정보를 공유할 수 있음

---

## 클라이언트 - 서버 모델

* **클라이언트**: 서버에게 필요한 요청을 보내고, 서버의 응답 결과를 받아 사용
* **서버**: 클라이언트의 요청을 받아, 적절한 응답을 반환

---

## URL (Uniform Resource Locater)

클라이언트가 서버에 요청을 보낼 때 적절한 요청이 필요.
→ 웹 상에서 특정 자원의 위치를 나타내는 주소

```
http://www.example.com:5833/cateory/food.html?topic=pizza
```

* **host([www.example.com](http://www.example.com))**: 리소스가 위치한 서버의 ip주소 또는 도메인
* **port(5833)**: 서버의 특정 네트워크 포트 번호
* **path(food.html)**: 서버 내에서 찾는 리소스 경로
* **query**: 서버에 추가적인 정보를 보내는 파라미터 (`?` 뒤에 key-value 형식으로 지정, `&` 기호로 구분)
* **scheme(protocol)**: 장치들 사이에서 통신하기 위한 규칙을 지정 → http

---

## HTTP

클라이언트와 서버가 어떻게 통신할지 정해놓은 규칙.

### 특징

* **무상태성**: 서버가 클라이언트의 이전 요청을 기억하지 않고 독립적으로 요청 처리
* **비연결성**: 클라이언트가 요청을 보내고 응답을 보내면 연결을 끊음

### HTTP 요청 (클라이언트가 보내는 구조)

* **start-line**: 요청 메서드, 요청 경로, HTTP 버전
* **headers**: 요청의 부가적인 정보
* **body**: 서버로 실제 전송되는 데이터

---

## HTTP의 메서드

메서드란? 서버의 자원에 대해 행하고 싶은 동사나 행위.

* **GET** : 리소스 조회
* **POST** : 리소스 추가, 등록
* **PUT** : 리소스 교체 (전체 수정)
* **PATCH** : 리소스 일부를 수정
* **DELETE** : 리소스 삭제

---

## HTTP 응답

* **status-line**: HTTP 버전, HTTP 상태 코드, 상태 메세지
* **headers**: 응답에 대한 부가정보
* **body**: 실제 데이터

---

## HTTP 상태 코드

* **200 OK** : 요청이 성공적으로 처리됨
* **201 Created** : 요청이 성공적으로 처리되어 새로운 리소스가 생성됨 (주로 post요청)
* **400 Bad Request** : 클라이언트의 요청이 잘못됨
* **404 Not Found** : 저장된 리소스를 찾을 수 없음
* **500 Internal Server Error** : 서버 내부 오류로 처리할 수 없음

---

## HTTP 접속 예시

* **client →** `GET/ http:/www.hongik.ac.kr` 자원을 요청하는 http메세지를 전송
* **server →** 요청된 자원을 찾아서 `200 ok` 의 상태코드와 함께 메인페이지의 응답 메세지를 body에 담아 응답

---

## 프론트엔드 / 백엔드

* **프론트엔드**: 사용자가 직접 보고 상호작용하는 사용자 인터페이스(UI)를 개발
* **백엔드**: 사용자의 요청을 받아 동작을 처리하고 데이터를 저장, 관리
  → DataBase에 저장됨
  → DBMS(MySQL, PosterSQL, MongoDB) 를 이용해 데이터베이스를 관리, 조작

클라이언트가 서버에 요청 → 데이터베이스의 정보를 가져와 → 클라이언트에 응답 전달 → 화면 렌더링

---

## API

* 클라이언트와 서버가 소통할 때 정해놓은 규칙과 기능의 목록
* 클라이언트는 http 메서드, url, request, http body 등을 어떻게 보내야 하고 서버는 어떠한 응답을 돌려줘야할지의 규약

---

## REST 방식

* HTTP의 장점을 최대한 활용할 수 있는 아키텍쳐

1. **자원(Resource)**

   * 고유한 아이디를 가짐, uri로 자원을 식별하는 문자열
2. **행위 (Method)**

   * 자원을 조작하기 위한 HTTP 메서드
3. **표현**

   * 어떠한 형식으로 데이터를 표현할지? 보통 JSON 형식

---

## JSON 형식

key-value로 설계한 형식

---

## Rest API

REST 원칙 기반으로.
자원을 고유한 URI로 식별하고 행위를 HTTP 메서드로 정의, 결과를 JSON 등의 표준 형식으로 표현한 API이다.

---

## 스프링 부트 실행 사진

![alt text](image.png)

---

### API 작성

## 회원 기능

1. **회원등록**

   * HTTP Method: POST
   * URI: `/members`

2. **회원리스트 조회**

   * HTTP Method: GET
   * URI: `/members`

3. **회원 상세 조회**

   * HTTP Method: GET
   * URI: `/members/{membeId}`

4. **회원 정보 수정**

   * HTTP Method: PATCH
   * URI: `/members/{memberId}`

5. **회원 삭제**

   * HTTP Method: DELETE
   * URI: `/members{memberId}`

---

## 상품 기능

1. **상품 정보 등록**

   * HTTP Method: POST
   * URI: `/products`

2. **상품 목록 조회**

   * HTTP Method: GET
   * URI: `/products`

3. **개별 상품 정보 상세 조회**

   * HTTP Method: GET
   * URI: `/products/{productId}`

4. **상품 정보 수정**

   * HTTP Method: PATCH
   * URI: `/products/{productId}`

5. **상품 삭제**

   * HTTP Method: DELETE
   * URI: `/products/{productId}`

---

## 주문 기능

1. **주문 정보 생성**

   * HTTP Method: POST
   * URI: `/orders`

2. **주문 목록 조회**

   * HTTP Method: GET
   * URI: `/orders`

3. **개별 주문 상세 조회**

   * HTTP Method: GET
   * URI: `/orders/{orderId}`

4. **주문 취소**

   * HTTP Method: DELETE
   * URI: `/orders/{orderId}`
