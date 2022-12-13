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
