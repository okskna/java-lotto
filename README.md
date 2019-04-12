# 로또 _ 우아한 테크코스 3주차 미션 _ ver2(미제출)

#### 기능 요구사항

- 로또 게임 기능을 구현한다.
- 로또 구입 금액을 입력하면 구입 금액에 해당하는 로또를 발급해야 한다.
- 로또 한장의 가격은 1000원이다.
- 로또 당첨 금액은 고정되어있다.
- 수익률을 계산해 출력한다.



#### 프로그래밍 요구사항

- 자바 코드 컨벤션을 준수한다.

- else 예약어를 사용하지 않는다.

- 접근제어자를 용도에 맞게 사용한다.

- 메소드의 길이가 10라인을 넘어가지 않도록 구현한다.

- indent를 1까지 허용한다.

- 메소드의 인자 수를 3개 까지 허용한다.

- 아래의 객체에 다음과 같은 요구사항을 만족시킨다.

  - ```java
    import java.util.List;
    /**
     * 로또 한장을 의미하는 객체
     */
    public class Lotto {
     private final List<Integer> numbers;
     public Lotto(List<Integer> numbers) {
     this.numbers = numbers;
     }
     // 추가 기능 구현
    }
    ```

    - 다음 Lotto 객체를 활용해 구현해야 한다.
    - Lotto 기본 생성자를 추가할 수 없다.
    - numbers 변수의 접근 제어자인 private을 변경할 수 없다.
    - Lotto에 필드(인스턴스 변수)를 추가할 수 없다.

  - ```java
    /**
     * 당첨 번호를 담당하는 객체
     */
    public class WinningLotto {
     private final Lotto lotto;
     private final int bonusNo;
     public WinningLotto(Lotto lotto,int bonusNo) {
     this.lotto = lotto;
     this.bonusNo = bonusNo;
     }
     public Rank match(Lotto userLotto) {
     // TODO 로직 구현
     return null;
     }
    }
    ```

    - 다음 WinningLotto객체를 활용해 구현해야 한다.
    - match() 메소드의 반환 값인 Rank는 저장소에서 제공한다.
    - WinningLotto 기본생성자를 추가할 수 없다.
    - lotto, bonusNo변수의 접근 제어자인 private을 변경할 수 없다.
    - WinningLotto에 필드(인스턴스변수)를 추가할 수 없다.



#### 프로그램 실행 예

![](img/LottoGameExample.jpg)



#### 구현 기능 목록

1. 사용자로부터 금액을 입력받는다.

   1-1. 입력받은 금액이 정상적이지 않는 경우에 대비한다.

2. 입력받은 금액만큼 로또를 객체화한다.

3. 객체화한 로또에 1~45 사이의 중복되지 않는 수를 6개 생성하여 넣는다.

4. 사용자로부터 지난 주 당첨 번호를 입력받는다.

   4-1. 당첨 번호는 1~45 사이의 수이며 중복될 수 없다.

5. 사용자로부터 보너스 볼 번호를 입력받는다.

   5-1. 보너스 볼 번호는 1~45 사이의 수이며 당첨 번호와 중복될 수 없다.

6. 당첨 번호와 사용자의 로또를 비교한다.

7. 결과를 이용해 통계를 내어 수익률을 계산한다.



#### 클래스

1. Main
   - public
     - statiac void main()
2. Game
   - public
     - void start()
3. Money: 금액 관리
   - field
     - final int money
   - public
     - Money(int money): 1000원 이상일 경우만 생성
   - private
4. UserLottos
   - field
     - final List<Lotto> userLottos
   - public
     - UserLottos(int count): count만큼 Lotto 객체 선언해서 ArrayList<Lotto>를 만든 후 userLottos에 저장
   - private
     - 
5. Lotto
   - field
     - final List<Integer> numbers
   - public
     - Lotto(List<Integer> numbers): numbers를 this.numbers에 저장
   - private
6. LottoNumber
   - field
     - final int number
   - public
     - LottoNumber(int number): number가 1~45 사이의 수 인지를 확인 후 this.number에 저장
   - private
7. WinningLotto
   - field
     - private final Lotto lotto
     - private final int bonusNo
   - public
     - WinningLotto(Lotto lotto, int bonusNo)
     - Rank match(Lotto userLotto)
   - private
8. Rank        //enum
   - field
     - private int countOfMatch
     - private int winningMoney
     - FIRST
     - SECOND
     - THIRD
     - FOURTH
     - FIFTH
     - MISS
   - public
     - static Rank valueOf(int countOfMatch, boolean matchBonus)
   - private
     - matchCount(int countOfMatch)
9. NumberGenerator
   - field
     - int number
   - public
     - NumberGenerator()
   - private
     - initRandomArray
     - getRandomNumber
10. User
    - field
    - pubic
    - private
11. Const
    - field

