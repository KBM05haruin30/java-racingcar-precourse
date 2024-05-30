# java-racingcar-precourse

***

### 과제 진행 요구 사항

- 미션은 자동차 경주 저장소를 포크하고 클론하는 것으로 시작한다.
- 기능을 구현하기 전 README.md 에 구현할 기능 목록을 정리해 추가한다.
- Git의 커밋 단위는 앞 단계에서 README.md 에 정리한 기능 목록 단위로 추가한다.
    - AngularJS Git Commit Message Conventions을 참고해 커밋 메시지를 작성한다

***
### MVC 패턴
- Model
  - 애플리케이션의 데이터 및 비즈니스 로직을 관리합니다.
  - 데이터베이스와 상호작용하고, 데이터를 조회, 삽입, 업데이트, 삭제하는 등의 작업을 수행합니다.
- View
  - 사용자 인터페이스를 담당합니다.
  - Model의 데이터를 사용자에게 보여주는 역할을 합니다.
- Controller
  - 사용자 입력을 처리하고, 그 입력을 기반으로 Model과 View를 업데이트하는 역할을 합니다.
  - 사용자 요청을 받아서 적절한 Model에 전달하고, Model로부터 데이터를 받아 View에 전달합니다.
***
### 구현해야 할 기능들
- 프로그래밍 요구 사항 3번에 MVC 패턴 기반으로 구현하라고 나와있으므로 Model, View, Controller 패키지를 만들어 줍니다.
- 각 기능들을 적절한 패키지에 넣는다.
- 자동차 클래스를 구현한다.
    - 자동차 클래스 안에는 이름과 이동한 거리를 알 수 있는 것이 있어야 한다.
- “경주할 자동차 이름을 입력하세요. (이름은 쉼표(, ) 기준으로 구분)” 을 출력한다.
- 사용자는 자동차 이름을 입력한다.
    - 자동차 이름은 쉼표(,)를 기준으로 구분하며 이름은 5자 이하만 가능하다.
    - 예시 : pobi, woni, jun
    - 구분한 값들 중 길이가 5초과(6이상)인 경우가 있거나 중복이거나 띄어쓰기가 있는 경우
        - illegalArgumentException를 발생시키고 “[ERROR] 자동차의 이름은 5자 이하만 가능합니다. 또한 자동차의 이름에 띄어쓰기가 있으면 안됩니다.”를 출력한다.
        - 다시 자동차 이름을 입력 가능하게 한다.
- “시도할 횟수는 몇회인가요?”를 출력한다.
- 사용자는 몇 번의 이동을 할 것인지를 입력한다.
    - 입력된 값이 정수가 아니면 InputMismatchException를 통해 "[ERROR] 입력 형식이 올바르지 않습니다. 정수로 입력해야 합니다."를 출력
    - 입력된 값이 1보다 작으면 illegalArgumentException를 발생시키고 “[ERROR] 시도 횟수는 1 이상이어야 합니다.”를 출력
    - 이동 횟수를 다시 입력 받는다.
- “실행 결과”를 출력한다.
- 사용자가 입력한 이동 횟수만큼 반복한다.
    - 각 자동차마다 전진 조건을 확인한다.
        - 자동차의 전진 조건은 0에서 9 사이에서 무작위 값을 구한 후 무작위 값이 4 이상일 경우이다.
        - 자동차가 전진할 시 -를 추가해서 출력한다.
    - 입력한 자동차의 이름과 이동한 거리를 같이 출력한다.
    - 예시는 다음과 같다.
        - pobi : -
        - woni :
        - jun : -
- 사용자가 입력한 이동 회수만큼 반복이 끝나면 최종 우승자를 정한다. 우승자는 한 명 이상일 수 있다. 우승자가 여러 명일 경우 쉼표(, )를 이용하여 구분한다.
- “최종 우승자 : “ 출력 + 우승한 자동차 이름 나열한다.

***

### 프로그래밍 요구 사항 1

- JDK 17 버전에서 실행 가능해야 한다.
- 프로그램 실행의 시작점은 Application 의 main() 이다.
- build.gradle 파일은 변경할 수 없으며, 제공된 라이브러리 이외의 외부 라이브러리는 사용하지 않는다.
- 프로그램 종료 시 System.exit() 를 호출하지 않는다.
- 프로그래밍 요구 사항에서 달리 명시하지 않는 한 파일, 패키지 등의 이름을 바꾸거나 이동하지 않는다.

***

### 프로그래밍 요구 사항 2

- 자바 코드 컨벤션을 지키면서 프로그래밍한다.
    - 기본적으로 Google Java Style Guide을 원칙으로 한다.
    - 단, 들여쓰기는 '2 spaces'가 아닌 '4 spaces'로 한다.
- indent(인덴트, 들여쓰기) depth를 3이 넘지 않도록 구현한다. 2까지만 허용한다.
    - 예를 들어 while문 안에 if문이 있으면 들여쓰기는 2이다.
    - 힌트: indent(인덴트, 들여쓰기) depth를 줄이는 좋은 방법은 함수(또는 메서드)를 분리하면 된다.
- 3항 연산자를 쓰지 않는다.
- 함수(또는 메서드)가 한 가지 일만 하도록 최대한 작게 만들어라.
- JUnit 5와 AssertJ를 이용하여 정리한 기능 목록이 정상적으로 작동하는지 테스트 코드로 확인한다.
    - 테스트 도구 사용법이 익숙하지 않다면 아래 문서를 참고하여 학습한 후 테스트를 구현한다.
        - JUnit 5 User Guide
        - AssertJ User Guide
        - AssertJ Exception Assertions
        - Guide to JUnit 5 Parameterized Tests

***

### 프로그래밍 요구 사항 3

- 함수(또는 메서드)의 길이가 15라인을 넘어가지 않도록 구현한다.
    - 함수(또는 메서드)가 한 가지 일만 잘 하도록 구현한다.
- else 예약어를 쓰지 않는다.
    - else를 쓰지 말라고 하니 switch/case로 구현하는 경우가 있는데 switch/case도 허용하지 않는다.
    - 힌트: if 조건절에서 값을 return하는 방식으로 구현하면 else를 사용하지 않아도 된다.
- 도메인 로직에 단위 테스트를 구현해야 한다. 단, UI(System.out, System.in, Scanner) 로직은 제외한다.
    - 핵심 로직을 구현하는 코드와 UI를 담당하는 로직을 분리해 구현한다.
    - 힌트: MVC 패턴 기반으로 구현한 후, View와 Controller를 제외한 Model에 대한 단위 테스트 추가에 집중한다.