# My Restaurant Record (나만의 맛집 기록)

> 방문한 맛집을 지도 위에 기록하고, 카테고리별로 깔끔하게 정리하여 관리하는 풀스택 웹 서비스입니다.

---

## 📸 프로젝트 미리보기 (Preview)

로그인 후 메인 화면으로 이동하여 저장된 맛집 리스트를 확인하는 전체적인 흐름입니다.

![메인 화면 이동 애니메이션](addgif.gif)

---

## 🛠 Tech Stack

### Backend
* Java 17
* Spring Boot
* Spring Data JPA
* BCrypt (Spring Security Crypto)
* Lombok
* Gradle

### Database
* MySQL
* H2 Database (개발용)

### Frontend
* HTML5 / CSS3
* JavaScript
* Kakao Maps API

---

## 🚀 주요 기능

### 1. 사용자 인증 및 개인화 서비스
회원가입 및 로그인 시스템을 통해 **사용자별로 독립적인 맛집 리스트**를 관리할 수 있습니다.

| 회원가입 화면 | 로그인 화면 |
| :---: | :---: |
| <img src="signup.png" width="400"> | <img src="login.png" width="419"> |

* **BCrypt 암호화**: 비밀번호는 해시 함수로 암호화되어 안전하게 저장됩니다.
* **세션 관리**: 로그인한 사용자만 본인의 기록에 접근할 수 있도록 세션을 통해 인증을 관리합니다.

### 2. 위치 기반 맛집 등록 및 수정
Kakao Maps API의 Geocoder 서비스를 통합하여, 가게 이름이나 주소 검색만으로 정확한 위치 좌표를 추출하고 지도 위에 마커를 표시합니다.

![맛집 등록 및 수정 화면](addRestaurant.png)
* **등록/수정 통합 UI**: 동일한 폼을 사용하여 직관적으로 정보를 입력하고 수정할 수 있습니다. (addRestaurant.png)

### 3. 스마트한 카테고리별 정리 및 필터링
등록된 맛집들을 **한식, 일식, 양식, 카페** 등 카테고리별로 자동 정리하여 보여줍니다.

![카테고리 필터링](category.png)
* `category.png`: 원하는 카테고리 버튼을 클릭하여 맛집을 빠르게 찾을 수 있습니다.

### 4. 메인 대시보드
지도 마커와 카드 리스트 형태로 시각화된 대시보드를 제공합니다.

![전체 대시보드](all.png)
* `all.png`: 상단 지도와 하단 리스트가 연동되어 표시됩니다.

---

## 💾 Database Architecture

### ERD 설계도
사용자 정보(`USER`)와 맛집 기록(`RESTAURANT`) 간의 **1:N 연관관계**를 객체 지향적으로 설계하고 JPA를 통해 매핑했습니다.

![ERD 설계도](erd2.png)

### 실제 저장 데이터 (SQL Console)
데이터베이스에 실제로 저장된 맛집 데이터의 모습입니다. 위 ERD에 맞게 데이터가 깔끔하게 저장되어 있음을 확인할 수 있습니다.

![SQL 실제 데이터](restsql.png)
* `sql_data.png`: MySQL Workbench 등에서 맛집 테이블의 데이터를 조회한 결과입니다.


