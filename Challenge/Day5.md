# TypeScript Challenge Day5 (12/18)

## TypeScript 로 객체지향 프로그래밍하기

</br>

<img width="254" alt="스크린샷 2022-12-18 오후 7 49 35" src="https://user-images.githubusercontent.com/94230809/208294152-1c3d73d5-6555-4527-9922-a5e21b9b519d.png">

</br>

이렇게 파라미터만 입력해주면 타입스크립트가 알아서 Constructor 함수를 만들어준다.</br>
위와 같이 private 혹은 public propety를 만들 수 있다.</br>
</br>

#### 타입스크립트 코드가 자바스크립트로 컴파일된 후 코드이다.

<img width="408" alt="스크린샷 2022-12-18 오후 7 51 07" src="https://user-images.githubusercontent.com/94230809/208294231-87910e8e-f651-4dd4-9f53-5d17faab03f0.png">
</br>

private부분은 자바스크립트로 컴파일되었을 때에는 보이지 않는다.

</br>

<img width="379" alt="스크린샷 2022-12-18 오후 7 53 22" src="https://user-images.githubusercontent.com/94230809/208294356-1e628188-4245-407e-994d-c26c5526084e.png">

</br>

이렇게 잘 작동한다.</br>
private과 public이 javascript에서 반영되지 않았더라도 TypeScript에서는 보호해줄것이다.

#### 만약 lastName을 보고싶어서 접근하게되면 어떻게 될까 ??

</br>

<img width="126" alt="스크린샷 2022-12-18 오후 7 56 10" src="https://user-images.githubusercontent.com/94230809/208294479-5fd97fd7-c59d-4b4a-8ba1-c10a9033da35.png">

</br>

접근되지 않는것을 볼 수 있다.</br>
이유는 private propety이기 때문이다. 우리가 접근할 수 있는 propety는 public인 nickName이 유일하다.

<img width="119" alt="스크린샷 2022-12-18 오후 7 57 06" src="https://user-images.githubusercontent.com/94230809/208294507-a77944e5-0f1f-4f24-a03e-2835c3fcbf01.png">

</br>
보다시피 에러가 나지 않는다.

---

</br>

## 추상 클래스 (Abstract Class)

다른 클래스가 상속받을 수 있는 클래스이다.</br>
새로운 인스턴스를 생성할 수 없다. 오직 다른곳에서 상속만 받을 수 있다.

</br>

<img width="255" alt="스크린샷 2022-12-18 오후 7 58 26" src="https://user-images.githubusercontent.com/94230809/208294551-b68e976d-1460-4ee8-bb6d-9c1bab99e8f4.png">

</br>
추상 클래스는 직접 새로운 인스턴스를 만들 수 없다.

</br>

<img width="367" alt="스크린샷 2022-12-18 오후 7 59 26" src="https://user-images.githubusercontent.com/94230809/208294604-e6c56e93-a4b0-463c-b295-ddcd0ba3f70a.png">

</br>

예를 들어서 위 처럼 새로운 인스턴스를 만들려고 하면 에러가 난다.</br>

이유는 타입스크립트가 추상클래스의 인스턴스를 만들 수 없다고 경고하기 때문이다.

<img width="382" alt="스크린샷 2022-12-18 오후 8 00 32" src="https://user-images.githubusercontent.com/94230809/208294652-734cd596-f74a-431e-b9ef-cfc762e9b4df.png">

</br>
다시 클래스 이름을 Player로 고쳐보면 잘 작동하고 nickName에 접근도 가능하다.

</br>

### 추상클래스 안에서 함수 만들기

<img width="381" alt="스크린샷 2022-12-18 오후 8 02 51" src="https://user-images.githubusercontent.com/94230809/208294744-3eea3340-a6b5-4a66-b020-1eaa5d21f031.png">

</br>
그럼 우리는 알다시피 Player 클래스는 User로 부터 상속 받았기 때문에 Player는 getFullName함수를 사용할 수 있다.

</br>

### 추상 메소드 만들기

추상클래스 안에서는 추상메서드를 만들 수 있다.</br>
하지만 추상메서드를 만들때에는 메서드를 구현하는것이 아니라, call signature만 적어둬야 한다.

#### 우리는 만약 User클래스 에서 추상메서드를 만들고자 할때 어떻게 해야할까.

<img width="659" alt="스크린샷 2022-12-18 오후 8 04 48" src="https://user-images.githubusercontent.com/94230809/208294823-36e2ac0c-0ee1-4ee2-9ef8-2a2420082aaf.png">

이렇게 했을 때 User클래스를 상속 받고 있는 Player클래스 에서는 에러가 발생한다.</br>
이유는 Player가 getNickName을 사용하고 있지 않기 때문이다.

<img width="390" alt="스크린샷 2022-12-18 오후 8 07 21" src="https://user-images.githubusercontent.com/94230809/208294940-5b05fa17-bebd-40bb-807e-18ac7f061680.png">

</br>

#### 우리는 여기서 getNickName함수가 console.log()로 nickName을 찍는 함수로 만들고 싶다.

</br>

<img width="264" alt="스크린샷 2022-12-18 오후 8 12 01" src="https://user-images.githubusercontent.com/94230809/208295106-8b4cc034-ae65-4ce4-b6da-15999f3029ff.png">

하지만 이렇게 에러가발생한다. </br>
왜냐하면 User 클래스에서 우리는 nickName을 private으로 만들었기 때문이다.
</br>
propety를 private 으로 만든다면, 그 클래스를 상속 받았을지라도 해당 propety에 접근 할 수 없다.

</br>
만약 외부로 부터 보호되지만 다른 자식 클래스에서는 사용되기를 원한다면, private을 사용하지 않아야한다.</br>
대신 protected를 사용해야한다.

</br>

아래와 같이 사용되는 것을 볼 수 있다.

<img width="453" alt="스크린샷 2022-12-18 오후 8 14 14" src="https://user-images.githubusercontent.com/94230809/208295196-8d98953a-19ff-4f63-805b-69428e498f60.png">

---

### 단어사전 만들기

</br>

<img width="702" alt="스크린샷 2022-12-18 오후 8 15 37" src="https://user-images.githubusercontent.com/94230809/208295264-673b7c76-f325-42a8-8203-7e89d2b8f382.png">

</br>

전에는 본 적 없던 형식인데, 제한된 양의 propety 혹은 key를 가지는 타입을 정의해 주는 방법이다.</br>
propety의 이름은 모르지만, 타입만을 알 때 사용할 수 있다.
</br>
</br>
</br>
예를 들어 Words타입의 dict를 하나 만들면 아래와 같이 들어갈 수 있을 것이다.

<img width="594" alt="스크린샷 2022-12-18 오후 8 17 07" src="https://user-images.githubusercontent.com/94230809/208295353-845fed99-adef-4b90-9ba7-26867563b575.png">

</br>
</br>
아래 Dict를 보면 에러가 발생해있다. 이유는 initializer가 없고 Constructor에서 정의된 것이 아니라고 한다.

</br>
<img width="555" alt="스크린샷 2022-12-18 오후 8 19 02" src="https://user-images.githubusercontent.com/94230809/208295420-c858bf04-0dd6-491e-8ddb-689140ba740a.png">

</br>

아래와 같은 방식으로 Constructor에 포함시켜준게 아니라는 뜻이다.

<img width="220" alt="스크린샷 2022-12-18 오후 8 19 57" src="https://user-images.githubusercontent.com/94230809/208295456-1aa450d0-8a62-4fcf-967b-c8a56cb3f683.png">

</br>

#### 그럼 어떻게 해야할까 ? 우리는 Constructor가 words를 지정해주기를 원한게 아니기 때문에 위처럼 하면 안된다.</br>

그럼 우리는 words를 initializer 없이 선언해주고 Constructor에서 수동으로 초기화시켜줄 것이다.

<img width="420" alt="스크린샷 2022-12-18 오후 8 21 25" src="https://user-images.githubusercontent.com/94230809/208295535-3430c788-0819-4a4c-9e31-fe19e8339618.png">

</br>

이렇게 우리는 Word 클래스 까지 만들었다.
</br>
</br>

#### 단어를 추가하기 위한 메서드를 만들어보자.

<img width="570" alt="스크린샷 2022-12-18 오후 8 22 36" src="https://user-images.githubusercontent.com/94230809/208295603-63541010-fb5b-4b18-a868-01479be24d30.png">

에러 없이 동작하는 add함수를 만들었다.
</br>
</br>

#### term을 이용하여 def를 찾는 메서드를 만들어보자.

</br>
<img width="571" alt="스크린샷 2022-12-18 오후 8 24 59" src="https://user-images.githubusercontent.com/94230809/208295729-3c612ebf-5b03-4e06-be73-affdc42564b1.png">

</br>
잘 작동하는지 컴파일된 자바스크립트 코드를 콘솔창에 입력해보려고 한다.

</br>
<img width="565" alt="스크린샷 2022-12-18 오후 8 26 53" src="https://user-images.githubusercontent.com/94230809/208295812-3eba2462-9a0b-45d0-abdb-a7051634e904.png">

</br>
잘 작동하는 것을 볼 수 있다.
