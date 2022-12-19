# TypeScript Challenge Day6 (12/19)

## interface

type과 비슷하지만 약간의 차이점이 있다.

### type 에서 interface로 변경

<img width="695" alt="스크린샷 2022-12-19 오후 8 57 57" src="https://user-images.githubusercontent.com/94230809/208420948-35a30b04-92eb-4591-97b1-cb5e13c91793.png">

</br>

#### type , interface 모두 똑같이 동작한다.

<img width="206" alt="스크린샷 2022-12-19 오후 8 58 32" src="https://user-images.githubusercontent.com/94230809/208421056-38d73e15-d9fa-4592-a635-a147dc05babe.png">

</br>

type은 내가 원하는 모든 값이 될 수 있다.</br>

Team 과 Helath 처럼 내가 정한 숫자 혹은 문자열 배열 등 내가 원하는 모든 값으로 정할 수 있다.</br>

그리고 Player처럼 object의 모양을 특정하는데 사용할 수 있다.
</br></br>
인터페이스는 오직 한가지의 용도만을 가지고 있다.</br>

오브젝트의 모양을 특정해주기 위한 것이다.</br>
</br>
타입스크립트에게 오브젝트의 모양을 알려주는 방법은 interface와 type이다.

다른 점은 type키워드는 interface 키워드에 비해 활용할 수 있는 게 많다.

#### interface에서는 아래와 같이 작동하지 않는다. </br>오로지 오브젝트의 모양을 타입스크립트에게 설명해 주는 하나의 목적이다.

<img width="192" alt="스크린샷 2022-12-19 오후 9 03 34" src="https://user-images.githubusercontent.com/94230809/208421949-ed673b12-1346-4849-a46f-13805513983e.png">

</br>
</br>

### interface는 class와 닮아있다.

<img width="235" alt="스크린샷 2022-12-19 오후 9 09 15" src="https://user-images.githubusercontent.com/94230809/208422919-9b30efb1-8bf3-43db-b011-ac4f08d60861.png">

interface를 이렇게 type으로도 바꿀수 있다. 보다시피 똑같이 동작하지만 조금 다르게 생겼다.</br>
타입스크립트에게 오브젝트임을 알려줄때는 인터페이스를 사용하는걸 더 추천한다.</br>
이렇게 하는 방법이 더 객체지향 프로그래밍처럼 보이기 때문이다.
</br>
</br>

### 인터페이스의 다른 장점은 property의 축적이다.

<img width="179" alt="스크린샷 2022-12-19 오후 9 11 46" src="https://user-images.githubusercontent.com/94230809/208423407-89857975-7987-4c40-9705-e5e815a06fa5.png">
</br>
</br>

같은 이름의 인터페이스를 3개를 작성해도 타입스크립트가 하나로 합쳐준다. 유용한 기능이고, type에서는 불가능한 일이다.

</br>

### 추상클래스 와 인터페이스

<img width="865" alt="스크린샷 2022-12-19 오후 9 14 11" src="https://user-images.githubusercontent.com/94230809/208423818-54328111-5529-4812-87c6-4682c71a5ce0.png"></br>

우리는 위 추상 클래스 코드를 interface로 바꿔보려한다.
</br>

interface는 자바스크립트에는 없는 단어이기 때문에 자바스크립트 코드에서는 보이지않는다.</br>

<img width="227" alt="스크린샷 2022-12-19 오후 9 19 42" src="https://user-images.githubusercontent.com/94230809/208424746-4ee9c0c9-09c0-463f-966c-90ae75f73f48.png"></br>

우리는 Player클래스에 User인터페이스를 상속할때 extends 대신 implement라는 자바스크립트에서는 사용하지 않는 단어를 쓸것이다.</br>

implement를 사용하면 자바스크립트 코드가 훨씬 가벼워진다.

자바스크립트 코드에서는 위 User인터페이스를 추적할 수 없는데 이건 위에서 말했다시피 인터페이스는 타입스크립트에서만 존재하기 때문이다.

Player클래스에 에러가 발생했다. Player 클래스에 User 인터페이스를 상속시키고 누락된 property를 채워 만족시켜보자.

<img width="423" alt="스크린샷 2022-12-19 오후 9 23 16" src="https://user-images.githubusercontent.com/94230809/208425373-bbb5d646-186f-4be9-88e0-63df47d111bd.png">

위 처럼 모든 property를 채웠다 하지만 에러가 발생한다.</br>
인터페이스를 상속받을때는 public으로 사용해야한다.

<img width="427" alt="스크린샷 2022-12-19 오후 9 24 43" src="https://user-images.githubusercontent.com/94230809/208425598-d69a895a-120f-4076-9014-6137779d942a.png">

이렇게 에러가 사라지는 것을 볼 수 있다.</br></br>
또 자바스크립트 코드를 보면 더이상 추상 클래스를 추가로 사용하지 않고 있다.</br>
파일 사이즈를 줄이고 싶다면 이런걸 원할 것이다.</br>
보다시피 인터페이스는 고유의 사용처가 있다.</br>
인터페이스는 클래스의 모양을 알려준다는 점에서 엄청 유용하다.</br>
그러면서도 자바스크립트 코드로 컴파일되지 않는다.</br>
인터페이스를 상속하는 것의 문제점 중 하나는 private property들을 사용하지 못한다는것이다.</br>

</br>

### 우리는 한 클래스에서 여러개의 인터페이스를 상속 받을수 있다?

<img width="421" alt="스크린샷 2022-12-19 오후 9 26 13" src="https://user-images.githubusercontent.com/94230809/208425867-0d73dad7-6b46-4b48-a8e8-ba8f28d4f616.png">

</br>

### 인터페이스를 타입으로 지정할 수 있다?

당연한 말 이다.

<img width="221" alt="스크린샷 2022-12-19 오후 9 28 01" src="https://user-images.githubusercontent.com/94230809/208426182-afb7c727-fe10-4d5b-9bed-f7ca08b5c413.png">

이렇게 지정 할 수 있다.
</br>

#### 만약 리턴 타입까지 인터페이스로 정해준다면

<img width="265" alt="스크린샷 2022-12-19 오후 9 31 11" src="https://user-images.githubusercontent.com/94230809/208426707-bd67afaf-a057-4a19-a9cb-fff35052136f.png">

</br>

인터페이스를 그대로 리턴해주면된다.

---

## 정리

인터페이스는 원하는 메서드와 property를 클래스가 가지도록 강제할 수 있게 해준다.</br>

인터페이스는 자바스크립트로 컴파일되지 않는다.</br>

추상클래스와 비슷한 보호를 제공하지만 , 인터페이스는 자바스크립트 파일에서 보이지 않는다.</br>

만약 추상 클래스를 다른 클래스들이 특정 모양을 따르도록 하기 위한 용도로 쓴다면 인터페이스를 사용하는것이좋다.</br>

상속시 extends 대신 implements를 사용하자. </br>

implements를 사용하면 자바스크립트 파일에서 코드 및 용량이 훨씬 줄어든다.</br>

인터페이스는 동일한 이름으로 중복생성이 가능하다. 타입스크립트가 축적 해준다.
