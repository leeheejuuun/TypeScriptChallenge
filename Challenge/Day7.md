# TypeScript Challenge Day7 (12/20)

## 다형성

다형성을 이룰수 있는 방법은 제네릭을 사용하는 것이다.</br>

제네릭은 placeholder 타입을 쓸 수 있도록 해준다.</br>

concrete 타입이 아니라 placeholder 타입이다.</br>

때가 되면 타입스크립트가 placeholder타입을 concrete타입으로 바꿔 줄 것이다.</br>

그렇기에 concrete타입 쓸 필요없이 그냥 placeholder를 사용하면 된다.

</br>

### 브라우저에서 사용하는 로컬스토리지 API 만들기

<img width="540" alt="스크린샷 2022-12-20 오후 11 46 42" src="https://user-images.githubusercontent.com/94230809/208694229-96ac8534-7421-4c64-ba37-d73f367c3a8c.png">

#### set , remove , get , clear 메서드 만들기

<img width="541" alt="스크린샷 2022-12-20 오후 11 48 48" src="https://user-images.githubusercontent.com/94230809/208694636-64eb5451-9860-4275-9c35-cd4cd5d85e04.png">

</br>
우리는 제네릭을 사용하여 로컬스토리지 API를 따라해 보았다.

</br>
위 LocalStorage를 사용하려면 아래와 같이 사용하면된다.

</br>
</br>
<img width="353" alt="스크린샷 2022-12-20 오후 11 49 40" src="https://user-images.githubusercontent.com/94230809/208694838-532893fd-775c-4571-9e89-ab0c435432ef.png">

</br>

이렇게 stringStorage를 만들고 타입을 string으로 명시해줬다. 이말은 즉

<img width="506" alt="스크린샷 2022-12-20 오후 11 51 11" src="https://user-images.githubusercontent.com/94230809/208695197-1bdae3d6-1c8e-4802-80da-dafa9d1506ac.png">

</br>

string을 보내고 string을 받겠다는 뜻이다.</br>

<img width="431" alt="스크린샷 2022-12-20 오후 11 52 19" src="https://user-images.githubusercontent.com/94230809/208695457-78105853-f671-4531-b906-d11435e45113.png">

우리가 만든 class에서 get을 보면 string을 받고 T를 보낸다고 적혀있다.</br>

놀랍게도 타입스크립트는 제네릭을 바탕으로 call signature를 만들어준다.</br>

이것이 바로 처음에 얘기했던 타입스크립트가 placeholder타입을 concrete타입으로 바꿔 준다. 라는 것이다.
</br>
</br>
</br>
숫자를 받는 numberStorage를 만들어보자.

<img width="502" alt="스크린샷 2022-12-20 오후 11 53 45" src="https://user-images.githubusercontent.com/94230809/208695820-e9471aa7-040d-459f-aa99-feb4ba41bc49.png">

보다시피 string을 보내고 number를 받는다.
