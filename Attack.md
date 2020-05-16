### Bruteforce
* Attack
  - 위치 : 로그인 페이지 등 인증을 통해 권한 획득이 가능한 곳
  - 조건 : 인증, 사용자 입력
  - 공격 형태
    > Alphabetical Order
    > Dictionary Attack
  - 특징 : 반복 수행
  - 목표 : 비밀번호 획득
* Depend
  - 비밀번호 복잡도를 높인다. 
  - 유추가 쉬운, 잘알려진 형태의 비밀번호 사용을 제한한다. 
  - 주기적으로 비밀번호를 변경한다. 
  - 사이트 별 비밀번로를 다르게 한다. 
  - 자동화된 동작 접근을 차단한다. 
  - 네트워크 구간 내 암호화 후 전송한다. 
  - Session ID를 암호화 후 저장한다. 
  - 유추 불가능한 고유 Session ID 를 사용한다. 
  - Session ID 재사용을 금지한다. 
  - Invalid Session ID 는 즉시 파기한다. 
  - 로그인 횟수를 제한한다. 
  - 반복된 로그인 실패시 응답 시간을 지연하거나, 계정을 잠그거나, CAPTCHA 를 적용한다. 
  - MFA 를 적용한다. 

### Command Injection
* Attack
  - 위치 : 서버로 입력값을 전달할 수 있는 웹 페이지
  - 조건 : 사용자 입력
  - 목표 : 서버 정보 수집, 권한 상승
* Depend
  - 입력값을 검증한다. 

### CSRF (with XSS)
* Attack
  - 위치 : 웹 페이지, 이메일 등
  - 조건 : 피해자가 대상 사이트에 로그인된 상태, 로그인 상태의 토큰
  - 형태 : Referer 주소 검증 우회를 위해 해킹된 사이트를 활용
  - 특징 : 피싱에 활용
  - 목표 : 사용자 비밀번호 변경, 사용자 권한 획득
* Depend
  - Header 내 Referer 주소가 서버 주소와 동일한지 비교한다. 
  - 랜덤한 CSRF Token 을 사용한다. 
  - 기본 비밀번호을 확인한다. 
  - CAPTCHA 를 적용한다. 
  - (관리자를 위해) CSRF 토큰과 같은 인증을 지원한다. 
  
### File Inclusion 
* Attack
  :: 지정한 파일을 소스코드 내 삽입하는 공격으로 PHP 에서 주로 발생함
  - 형태
    > Local File Inclusion ( LFI ) : 이미 내부(시스템)에 있는 파일을 Include 해 원하는 동작을 실핼하는 방법
    > Remote File Inclusion ( RFI ) : 외부에 있는 파일을 Include 해 원하는 동작을 실행하는 방법
* Depend
  - 사용자 입력을 통해 Include 파일이 전달되지 않도록 한다. 
  - 필요한 파일만 Include 될 수 있도록 검사한다. 

### File Upload (with File Inclusion)
* Attack 
  :: 파일 업로드 페이지를 이용해 악성 파일 (웹쉘)을 업로드 후 실행하는 공격 
* Depend
  - 업로드된 파일을 라이브러리등을 통해 직접 재 생생해 우회를 차단한다.
  - 업로드된 파일명을 랜덤하게 만들어 직접 접근이 불가능하도록 한다. 
  - 파일이 저장되는 서버를 웹 어플리케이션 서버와 물리적으로 분리한다. 
  - 업로드된 파일이 저장되는 폴더의 실행 권한을 제거한다. 

### Etc
* Path Traversal