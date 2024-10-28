# javascript-calculator-precourse

<br/>

#  프리코스 2주차 과제 (자동차 경주)

## ✅ 기능 요구 사항

입력한 문자열에서 숫자를 추출하여 더하는 계산기를 구현한다.

- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- 각 자동차에 이름을 부여할 수 있다. 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
- 자동차 이름은 쉼표(,)를 기준으로 구분하며 이름은 5자 이하만 가능하다.
- 사용자는 몇 번의 이동을 할 것인지를 입력할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 무작위 값을 구한 후 무작위 값이 4 이상일 경우이다.
- 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한 명 이상일 수 있다.
- 우승자가 여러 명일 경우 쉼표(,)를 이용하여 구분한다.
- 사용자가 잘못된 값을 입력할 경우 "[ERROR]"로 시작하는 메시지와 함께 Error를 발생시킨 후 애플리케이션은 종료되어야 한다.

### 입출력 요구 사항

입력

- 경주할 자동차 이름(이름은 쉼표(,) 기준으로 구분)

  > pobi,woni,jun

- 시도할 횟수
  > 5

출력

- 차수별 실행 결과

  > pobi : -- <br>
  > woni : ---- <br>
  > jun : ---

- 단독 우승자 안내 문구

  > 최종 우승자 : pobi

- 공동 우승자 안내 문구
  > 최종 우승자 : pobi, jun

실행 결과 예시

> 경주할 자동차 이름을 입력하세요.(이름은 쉼표(,) 기준으로 구분)
> pobi,woni,jun
> 시도할 횟수는 몇 회인가요? <br>
> 5
>
> 실행 결과 <br>
> pobi : - <br>
> woni : <br>
> jun : - <br> <br>
> pobi : --<br>
> woni : -<br>
> jun : --<br> <br>
> pobi : ---<br>
> woni : --<br>
> jun : ---<br> <br>
> pobi : ----<br>
> woni : ---<br>
> jun : ----<br> <br>
> pobi : -----<br>
> woni : ----<br>
> jun : -----<br> <br>
> 최종 우승자 : pobi, jun

<br/>
<br/>

## ✅ 라이브러리

- [O] @woowacourse/mission-utils에서 제공하는 Console API를 사용하여 구현해야 한다.
- [O] 사용자의 값을 입력 및 출력하려면 Console.readLineAsync()와 Console.print()를 활용한다.

<br/>
<br/>

## ✅ 과제 요구 사항 체크리스트

- [O] 문자열 덧셈 계산기 저장소를 fork하고 clone하는 것으로 시작한다.
- [O] 기능을 구현하기 전 [README.md](http://README.md) 에 구현할 기능 목록을 정리해 추가한다.
- [ ] Git의 커밋 단위는 앞 단계에서 [REAME.md](http://REAME.md) 에 정리한 **기능 목록 단위로 추가**한다.

  - [ ] [AngularJS Git Commit Message Conventions](https://gist.github.com/stephenparish/9941e89d80e2bc58a153)을 참고해 커밋 메시지를 작성한다.

- [ ] indent(인덴트, 들여쓰기) depth를 3이 넘지 않도록 구현한다. 2까지만 허용한다.
  - 예를 들어 while문 안에 if문이 있으면 들여쓰기는 2이다.
  - 힌트: indent(인덴트, 들여쓰기) depth를 줄이는 좋은 방법은 함수(또는 메서드)를 분리하면 된다.
- [ ] 3항 연산자를 쓰지 않는다.
- [ ] 함수(또는 메서드)가 한 가지 일만 하도록 최대한 작게 만들어라.
- [ ] Jest를 이용하여 정리한 기능 목록이 정상적으로 작동하는지 테스트 코드로 확인한다.
  - [ ] 테스트 도구 사용법이 익숙하지 않다면 아래 문서를 참고하여 학습한 후 테스트를 구현한다.

사용 예시

- 0에서 9까지의 정수 중 한 개의 정수 반환
  > MissionUtils.Random.pickNumberInRange(0, 9);

<br/>
<br/>

## ✅ 구현 기능 목록

### 1️⃣ 사용자 입력

- [ ] **자동차 이름 입력 메시지 출력**

  - 사용자에게 "경주할 자동차 이름을 입력하세요.

    > ❕(이름은 쉼표(,) 기준으로 구분)" 메시지를 출력한다.

    > ❕ 이름 입력은 비동기 방식으로 `Console.readLineAsync`를 사용하여 받는다.

- [ ] **이동 횟수 입력 메시지 출력**

  - 사용자에게 "시도할 횟수는 몇 회인가요?" 메시지를 출력한다.
    > ❕이동 횟수도 비동기로 `Console.readLineAsync`를 사용해 입력을 받는다.

### 2️⃣ 입력 처리

- [ ] **자동차 이름 유효성 확인**

  - 각 자동차 이름이 5자 이하인지 확인한다. 5자를 초과하는 경우 `[ERROR] 자동차 이름은 5자 이하만 가능합니다.` 메시지를 출력하고 프로그램을 종료한다.
  - 이름이 쉼표로 구분되지 않거나, 유효하지 않은 값이 포함된 경우 `[ERROR] 잘못된 입력입니다.`를 출력하고 프로그램을 종료한다.

- [ ] **이동 횟수 유효성 확인**

  - 이동 횟수가 숫자인지 확인한다. 숫자가 아닌 경우 `[ERROR] 잘못된 입력입니다.` 메시지를 출력하고 프로그램을 종료한다.

### 3️⃣ 게임 로직

- [ ] **자동차 전진 조건 설정**

  - 0에서 9까지의 숫자 중 무작위 값을 생성하고, 해당 값이 4 이상일 경우에만 전진하도록 설정한다.
    > ❕ `MissionUtils.Random.pickNumberInRange(0, 9);`를 활용하여 무작위 값을 생성한다.

- [ ] **자동차 전진**

  - 설정된 조건에 따라 각 자동차가 전진하거나 멈추도록 하여 매 시도마다 자동차의 위치를 갱신한다.

### 4️⃣ 결과 출력

- [ ] **차수별 실행 결과 출력**

  - 각 자동차의 이름과 전진 거리를 `-` 문자로 표시하여 출력한다.
  - 예시: `pobi : ---`

- [ ] **우승자 결정 및 출력**

  - 모든 시도가 완료된 후 가장 많이 전진한 자동차를 우승자로 결정한다.
  - 우승자가 여러 명일 경우 쉼표로 구분하여 출력한다.
  - 예시 (단독 우승자): `최종 우승자 : pobi`
  - 예시 (공동 우승자): `최종 우승자 : pobi, jun`

### 5️⃣ 예외 처리

- [ ] **잘못된 입력 예외 처리**

  - 잘못된 이름 형식, 이동 횟수, 전진 조건에 대한 예외 처리를 수행한다.
  - 예외 발생 시 "[ERROR]" 메시지를 출력하고 프로그램을 종료한다.
