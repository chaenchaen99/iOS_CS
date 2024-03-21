## closer

클로저 표현식은 독립적인 코드 블록이다.


let multiply = {(_ val1: Int, _ val2: Int) -> Int in
    return val1 * val2
}

let result = multiply(10,20)

클로저 표현식은 비동기 메서드 호출에 대한 완료 핸들러를 선언할 때 종종 사용된다.
예를 들어, iOS 앱을 개발할 때 어떤 작업을 백그라운드에서 작업하게 해서 앱이 다른 작업을 계속할 수 있도록 
운영체제에게 요청해야 하는 경우가 종종 생긴다.
이런 경우에는 보통 시스템이 앱에게 작업이 완료된 것을 알리고 작업을 호출할 때 선언했던 완료 핸들러를 호출하여 결과를 반환한다.
완료 핸들러에 대한 코드는 주로 클로저 표현식의 형태로 구현된다.

eventstore.requestAccess(to: .reminder, completion: {(granted: Bool, error: Error?) -> Void in
    if !granted {
        print(error!.localizedDescription)
    }
})

requestAccess(to:) 메서드 호출로 수행된 작업이 완료되면, completion: 매개변수로 선언된 클로저 표현식이 실행된다.
다음의 선언부와 같이 이 완료 핸들러는 불리언 값과 Error 객체를 변수로 받으며 아무런 결과도 반환하지 않는다.

클로저 표현식의 선언부를 다음과 같이 간략하게 나타낼 수 있다.

eventstore.requestAccess(to: .reminder, completion: {(granted, error) in
    if !granted {
        print(error!.localizedDescription)
    }
})