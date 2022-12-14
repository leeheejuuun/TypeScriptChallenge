# TypeScript Challenge Day3 (12/14)

## 함수의 Call Signatures

우리는 함수에 타입을 설정할때 아래 두가지 방식을 흔히 사용할 것이다.

<img width="286" alt="스크린샷 2022-12-14 오후 5 24 11" src="https://user-images.githubusercontent.com/94230809/207543792-5f12f45d-20df-47cb-96ac-6de7dfdf47ed.png">
</br>

하지만 우리는 타입을 함수에 직접 적지않고 call signature를 사용해볼것이다.</br>
call signature는 우리가 함수위에 마우스를 올렸을 때 나타나는 함수의 인자 타입과 반환타입을 말한다.
</br></br>
아래 사진과 같이 말이다.</br>
<img width="384" alt="스크린샷 2022-12-14 오후 5 25 51" src="https://user-images.githubusercontent.com/94230809/207544123-363b692d-dcd8-4b87-87bd-00980ece4ee3.png"></br>

## call signature 사용 방법

### 1. call signature를 사용하기 위해 함수의 인자와 반환타입을 먼저 생각하여 타입을 생성해준다.</br>

<img width="295" alt="스크린샷 2022-12-14 오후 5 28 05" src="https://user-images.githubusercontent.com/94230809/207544632-570286fa-52f1-42db-b071-ec000e3eea76.png">
</br>
</br>

### 2. 그리고 아래 사진과 같이 우리가 함수에 타입을 설정해주는것과 동일하게 입력해주면 끝이다.</br>

</br>
<img width="204" alt="스크린샷 2022-12-14 오후 5 29 23" src="https://user-images.githubusercontent.com/94230809/207544902-77499480-ff69-4689-b9b9-21157ae4764d.png"></br>
(이제 타입스크립트는 add함수가 call signature를 통해 Add라는 타입을 가지고있다는 것을 알고있을것이다.)
</br>
</br>

### 3. 주의 할 점

<img width="243" alt="스크린샷 2022-12-14 오후 5 31 42" src="https://user-images.githubusercontent.com/94230809/207545465-ab574e61-937a-4247-82fd-21aa5272bc14.png">

</br>
이렇게 a+b자리에 {}로 감싸게 된다면 에러가 날 뿐더러 리턴하지 않을 것이다.</br>
이유는 add1을 {}로 감싸는 순간 add1함수는 number를 반환해야하는 함수인데 void를 반환하고있다고 한다.</br>
void는 함수지만 값을 아무것도 리턴하지않는 함수이기 때문이다.

---

## Overloading

우리가 사용하고있는 패키지나 라이브러리 들은 대부분 overloading을 사용하고있다.</br>

overloading은 함수가 서로다른 여러개의 call signature를 가지고 있을 때 발생시킨다.

### 이해를 돕기위한 바보같은 예시

<img width="278" alt="스크린샷 2022-12-14 오후 5 34 17" src="https://user-images.githubusercontent.com/94230809/207546029-62c05a81-9cd2-4d50-b355-69b170554a2a.png">
</br>
</br>
우리는 여기서 add함수는 Add타입에서 1번 혹은 2번으로 부를 수 있다는 걸 알고있다.

</br>

에러를 확인해 보면 파라미터 b는 number혹은string이 될 수 있기에 string 과 number를 더할 수 없다고한다.</br>
이 때 우리는 아래와 같이 검증을 해줘야한다.

<img width="242" alt="스크린샷 2022-12-14 오후 5 35 40" src="https://user-images.githubusercontent.com/94230809/207546291-d647de03-14de-441f-b900-d2212edb5293.png">

</br>

이런 식 으로 말이다.
하지만 이건 매우 나쁜 코드이다. </br>아주 소수의 상황에서만 사용 가능하기때문이다.

### Next.js를 예시로 활용한 Overloading

<img width="222" alt="스크린샷 2022-12-14 오후 5 37 12" src="https://user-images.githubusercontent.com/94230809/207546670-b6c676f9-abcc-4b33-a5b7-fe45e6641f67.png">

이렇게 string으로 보내는 방식과 object로 보내는 두가지 방식이있다. 우리는 이러한 상황을 굉장히 많이 볼것이라고 한다.

</br> 이제 위 예시를 오버로딩해보자.

<img width="373" alt="스크린샷 2022-12-14 오후 5 39 23" src="https://user-images.githubusercontent.com/94230809/207547210-28315cd4-1fab-4a3f-b8a0-69014cc30727.png">
</br>

1. Config라는 객체를 타입으로 만들어 두고 Push에서 path와 config모두 리턴하지 않는 void로 잡아둔다.

2. 우리는 이제 push 함수를 만들 것 이다.

<img width="562" alt="스크린샷 2022-12-14 오후 5 41 50" src="https://user-images.githubusercontent.com/94230809/207547768-86271274-0c68-438f-94e5-034d0612158a.png">

</br>

3. push 함수에서 인수에 마우스를 올려보면 config는 string혹은Config객체를 받을 수 있다고 한다.</br>
(이제 우리는 체크해야한다 config가 string일때 혹은 아닐때)

   <img width="256" alt="스크린샷 2022-12-14 오후 5 43 12" src="https://user-images.githubusercontent.com/94230809/207548083-01c6c461-f96f-4a00-8f5f-0fa500dc6817.png">

</br>

오버로딩은 실제로 이런식으로 쓰여진다. 많은 패키지나 라이브러리에서 사용되고 있다고한다.
</br>

### 다른 여러개의 argument를 가지고 있는 경우의 Overloading

각각 다른 call signature에 파라미터의 개수도 다른 경우

<img width="296" alt="스크린샷 2022-12-14 오후 5 45 56" src="https://user-images.githubusercontent.com/94230809/207548649-90a7b492-6916-43c6-ba2c-0641707fb684.png">

</br>

에러가 발생한다. 이유는 다른 개수의 파라미터를 가지게 되면, 나머지 파라미터도 타입을 지정해줘야 한다.</br></br>
type = Add에서 c는 옵션같은것이다. </br>그렇기에 우리는 c는 아마도 들어오게 된다면 number일 것이다. 라는것을 알려줘야한다.

<img width="266" alt="스크린샷 2022-12-14 오후 5 47 28" src="https://user-images.githubusercontent.com/94230809/207549001-98ab6dc4-ddd3-4234-a90a-cc5a8a3d6c6f.png">

</br>
위 처럼 말이다.</br>
다시 정리해보면 아래와 같이 사용할 것이다.

</br>
<img width="274" alt="스크린샷 2022-12-14 오후 5 48 30" src="https://user-images.githubusercontent.com/94230809/207549241-725a218e-f6ef-4a6d-8c21-9ccb5895f508.png">
