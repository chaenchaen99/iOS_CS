##Typecasting

Typecasting에는 upcasting 과 downcasting이 있다.
업캐스팅은 특정클래스의 객체가 상위클래스들 중의 하나로 변형되는 것이다.
swift에서 업 캐스팅은 as 키워드를 사용하여 수행되며, 이러한 변환은 성공할 것이라고 컴파일러가 알려줄 수 있기 때문에 guaranteed conversion이라고 한다.

let myButton: UIButton = UIButton()
let myControl = myButton as UIControl

UIButton은 UIControl의 하위클래스이므로 위와 같이 안전하게 업캐스팅될 수 있다,

반면, 다운캐스팅은 어떤 클래스에서 다른 클래스로 만드는 변환이 일어날 때 발생한다.
이런 변환이 안전하게 수행된다거나 유효하지 않은 변환 시도를 컴파일러가 잡아낼 것이라는 보장을 할 수 없다.
다운캐스팅으로 유효하지 않은 변환을 했는데 컴파일러가 발견하지 못한다면, 대부분의 경우 런타임에서 에러가 발생할 것이다.

다운 캐스팅은 보통 어떤 클래스에서 그 클래스의 하위 클래스로 변환하게 된다.
다운 캐스팅은 as! 키워드로 수행되며, 이를 강제 변환(forced conversion)이라고 한다.

let myScrollView: UIScrollView = UIScrollView()
let myTextView = myScrollView as! UITextView()

위 코드는 UIScrollView를 UITextView로 변환할 수 없으니 실행중에 충돌이 발생할 것이다.
이것은 다운캐스팅의 위험성을 보여주는 예이다.
따라서 강제로 다운캐스팅을 할 때는 주의해서 사용해야 한다.

다운캐스팅을 하는 더 안전한 방법은 as?를 사용한 옵셔널 바인딩을 사용하는 것이다.
만약 변환이 성공적으로 수행된다면, 지정한 타입의 옵셔널 값이 반환될 것이며, 변환에 오류가 발생한다면 옵셔널 값은 nil이 될 것이다.

if let myTextView = myScrollView as? UITextView {
    print("Type cast to UITextView succeed")
}
else {
    print("Type cast to UITextView failed")
}


if키워드를 사용하여 타입 검사(TypeCheck)를 할 수도 있다.

if myObject is MyClass {
    
}

