# Spring Practice

김영한님의 인프런 강의 **[실전! 스프링 부트와 JPA 활용1 - 웹 애플리케이션 개발](https://inf.run/iS6G)**를 실습한 프로젝트입니다.  

프로젝트는 다음과 같은 환경에서 진행되었습니다.  
- m1 macbook air 13`
- mac os x moterey 12.3.1

## Getting Started
### install java 11
m1 칩셋이기 때문에 azul Zulu jdk를 사용하였습니다.  
설치 과정은 생략

### h2 database setting
1. h2 database 다운로드: [h2database.com](https://www.h2database.com/html/download.html)  
2. 압축 해제 및 해당 폴더로 이동
3. bin/h2.sh 실행
```aidl
cd bin
./h2.sh
```
4. 웹 콘솔 접속
- h2.sh 파일 실행 시 열린 웹 콘솔이 작동하지 않는다면 호스트를 localhost로 변경
- 데이터베이스 파일 생성 방법
  - `jdbc:h2:~jpashop`(최소 한 번, 세션키 유지한 상태로 실행)
  - `~/jpashop.mv.db`파일 생성 확인
  - 이후 부터는 `jdbc:h2:tcp://localhost/~jpashop` 접속

### intellij 설정
**lombok 적용**
1. Prefrences > plugin > lombok 검색 실행 (재시작)
2. Prefrences > Annotation Processors 검색 > Enable annotation processing 체크 (재시작)
3. 임의의 테스트 클래스를 만들고 @Getter, @Setter 확인

**IntelliJ Gradle 대신에 자바 직접 실행**
- Preferences > Build, Execution, Deployment Build > Tools Gradle
- Build and run using: Gradle > IntelliJ IDEA
- Run tests using: Gradle > IntelliJ IDEA  

### Build
프로젝트 경로로 이동 후 아래 명령어를 입력하여 gradlew 파일 실행  
clean은 옵j
```aidl
./gradlew clean build
```

빌드된 파일은 `build/libs`에 생성됨

아래 명령어로 빌드된 파일 실행
```aidl
cd build/libs
java -jar jpashop-0.0.1-SNAPSHOT.jar
```

[localhot:8080](localhot:8080) 접속

### Convention
- Commit Convention
```markdown
feat: 새로운 기능 추가
fix: 버그 수정
docs: 문서 수정
style: 코드 포맷 변경, 세미콜론 누락, 코드 변경 없음
refactor: 프로덕션 코드 리팩터링
test: 테스트 추가, 테스트 코드 리팩터링, 프로덕션 코드 변경 없음
chore: 빌드 테스크 업데이트, 패키지 매니저 환경설정, 프로덕션 코드 변경 없음
```
협업이 아닌 단순 기록용 프로젝트이므로 Git Convention은 생략