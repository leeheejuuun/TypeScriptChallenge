# TypeScript Challenge Day2 (12/13)

---

## Optional Parameter

여러 플레이어가 있다고 가정한 후 모든 플레이어가 name은 모두 가지고 있고 age를 가진 플레이어는 몇명 밖에 없다고 했을때 우리는 어떻게 해야할까 ?

<img width="148" alt="스크린샷 2022-12-13 오후 10 29 12" src="https://user-images.githubusercontent.com/94230809/207333862-2c4edf37-2d37-42a5-9063-3d7e2100317e.png">

이렇게 name과 age를 담을 수 있는 객체가 있다.</br>
이때 player객체는 에러를 밷는다 이유는 무엇일까 ?
이유는 간단하다.</br>name과 age를 담는 객체에 name만 담겨있기 때문이다.</br>

이를 해결하는 방법은</br>
<img width="153" alt="스크린샷 2022-12-13 오후 10 32 19" src="https://user-images.githubusercontent.com/94230809/207335318-192c89a1-1c87-4720-9333-1ceb95ef7e38.png"></br>

?옵션을 달아주는것이다. ?를 붙혀주면 아래와 같이 age는 number 혹은 undefined 를 갖게된다.
</br>

<img width="269" alt="스크린샷 2022-12-13 오후 10 35 22" src="https://user-images.githubusercontent.com/94230809/207336860-8fca843c-31e0-47bb-964b-1b0aa012bbea.png">

</br>

자, 그럼 player객체에서 age를 가지고 조건문을 만들어보자.

<img width="358" alt="스크린샷 2022-12-13 오후 10 38 26" src="https://user-images.githubusercontent.com/94230809/207338593-31de74e6-0fbf-488f-b20a-6b2606258a2d.png">

이때 조건은 에러가 발생한다. player.age는 undefined일 수 있다고 말이다.
</br></br>
그 말은 즉 우리는 아래 사진과 같이 &&연산자를 활용하여 player.age가 존재하는지 확인을 거쳐야한다.

<img width="243" alt="스크린샷 2022-12-13 오후 10 40 16" src="https://user-images.githubusercontent.com/94230809/207339621-5496efb2-c245-48e8-be63-5def37d09a79.png">

---

## type

우리는 100명 이상의 player가 있다고 가정해보자 </br>각 player마다 이러한 객체를 일일히 생성해주는 것은 불필요한 일이다.</br>
아마, 모든 개발자들은 적은 코드를 작성하고, 재사용 가능한 코드를 작성하고 싶어 할 것이다. </br>그 방법은 바로 타입을 생성하는 것이다.

<img width="139" alt="스크린샷 2022-12-13 오후 10 44 01" src="https://user-images.githubusercontent.com/94230809/207341859-9bdbe898-1283-4fa7-8f29-afd056a80dd2.png"></br>

이런 식 으로 공통으로 사용되는 것을 type으로 지정해 두고</br>

아래와 같이 지정해주면 된다.

<img width="202" alt="스크린샷 2022-12-13 오후 10 46 09" src="https://user-images.githubusercontent.com/94230809/207343074-5d7f5ef6-3e20-4c29-aa98-90b693356020.png">

</br>

### 함수의 리턴값 정해주기

</br>

나는 name을 갖는 object를 반환하는 함수를 만들려고 한다.

<img width="270" alt="스크린샷 2022-12-13 오후 10 50 48" src="https://user-images.githubusercontent.com/94230809/207345882-2341aaab-4577-4106-8c29-2f63cf7d3ef4.png">

이때 우리는 object에 age를 추가하고 싶다.
<img width="257" alt="스크린샷 2022-12-13 오후 10 55 13" src="https://user-images.githubusercontent.com/94230809/207348547-d3c7d85a-335c-496d-9777-1812964a2882.png"></br>하지만 작동하지 않는다. 이유는 playerMaker함수는 name을 갖는 object 를 리턴하기 때문이다.
</br>

해결 방법은 우리가 변수와 인수에 해준것과 같은 방법으로 함수명 뒤에 아까전에 만들어둔 type을 넣어주면 된다.

<img width="305" alt="스크린샷 2022-12-13 오후 10 56 54" src="https://user-images.githubusercontent.com/94230809/207349581-0a51cc69-d9c2-4b73-8956-295b7e76e508.png">

이제 잘 동작한다.</br>
그 이유는 이제 heejun이라는 변수가 Player 타입이라는 것을 알기 때문이다.

타입스크립트는 이제 playerMaker가 string타입으로 name을 받고 Player타입을 return하는 함수라는것을 알고있다.

</br>

### 화살표 함수 사용시 타입을 지정하는 법

</br>
<img width="394" alt="스크린샷 2022-12-13 오후 10 58 55" src="https://user-images.githubusercontent.com/94230809/207350659-41082651-471d-43a4-a706-b3372d20370e.png">

---

## Tuple

배열의 길이가 고정되고 각 요소의 타입이 지정되어 있는 배열 형식을 의미한다.

<img width="484" alt="스크린샷 2022-12-13 오후 11 00 38" src="https://user-images.githubusercontent.com/94230809/207351710-cb477105-cf57-4fb3-9087-3c7fd55ed55f.png">

항상 정해진 갯수의 요소를 가져야 하는 array를 지정할 수 있다는 것을 기억해야한다.

---

## any

any 는 타입스크립트의 보호장치를 비활성화 시킨다.

<img width="139" alt="스크린샷 2022-12-13 오후 11 02 15" src="https://user-images.githubusercontent.com/94230809/207352942-51e0d81e-f039-4e18-b8d8-92b8409556f1.png">

당연히 에러가발생하는 코드이다. 이때 any를 사용하면

<img width="188" alt="스크린샷 2022-12-13 오후 11 01 58" src="https://user-images.githubusercontent.com/94230809/207353397-794d393c-b60d-498a-888c-cc7a16bccb13.png">

위와 같이 에러가 발생하지 않는다.

any를 사용 할 때는 매우 신중하게 써야한다.</br>
하지만 종종 타입스크립트에게 에러를 밷지 말라고 해야할때는 이 any타입을 사용하면 될거 같다.</br>
절대 남발해서는 안된다. 그러면 우리는 자바스크립트를 사용하는것과 다를게 없다.

---

## unknown

어떤 타입인지 모를때는 unknown을 사용할 수 있다.

<img width="115" alt="스크린샷 2022-12-13 오후 11 05 50" src="https://user-images.githubusercontent.com/94230809/207354600-aaa4103f-b694-4007-b789-5179cbc55ca4.png">

</br>
위 와 같은 상황에서 에러가 발생한다.
</br>이유는 a는 unknown이므로 어떤 타입인지 모르기때문이다. 이럴때는 체크를 해줘야한다.
</br>
</br>
<img width="192" alt="스크린샷 2022-12-13 오후 11 07 12" src="https://user-images.githubusercontent.com/94230809/207354935-9264e341-e292-49b0-9ce1-ba8e90655b70.png">

위 와 같은 방식으로 검증이 필요하다. 만약 문자열로써 사용하고 싶다면 아래와 같이 사용할 수 있다.

<img width="196" alt="스크린샷 2022-12-13 오후 11 09 29" src="https://user-images.githubusercontent.com/94230809/207355465-ee930f26-7233-4a7d-a60a-c82b8fa889df.png">

---

## void

void는 아무것도 리턴하지 않는 함수에 발생한다.

<img width="239" alt="스크린샷 2022-12-13 오후 11 10 39" src="https://user-images.githubusercontent.com/94230809/207355805-417c5b9b-322b-4ef5-9450-7511139adf34.png">

---

## never

never은 함수가 절대 리턴하지 않을때 발생한다.

<img width="451" alt="스크린샷 2022-12-13 오후 11 12 07" src="https://user-images.githubusercontent.com/94230809/207356171-e92d1053-b04d-4af8-b0f0-187ed5e53d98.png">
</br>
</br>
아래 함수에서 우리는 name 은 string or number라고 명시해줬기 때문에 1번은 string 2번은 number일 것 이다.
</br></br>우리는 name을 string혹은number로 정해줬기에 타입이 정확하게 들어온다면 1,2번에서 검증 후 종료될것이다. 그렇기에 3번은 절대 실행되지 않아야하며, 3번의 name은 never타입이다.
</br></br>

<img width="306" alt="스크린샷 2022-12-13 오후 11 16 26" src="https://user-images.githubusercontent.com/94230809/207357212-c67a9c37-cb4b-4fc1-8c8a-2dd7bfb4b9a5.png">
