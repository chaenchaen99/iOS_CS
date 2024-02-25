##Optional

옵셔널 타입의 목적은 변수나 상수에 값이 할당되지 않은 상황을 처리하기 위해 안전하고 일관된 접근 방식을 제공하는 것.
--------------------------------------
강제 언래핑 방식: 옵셔널 데이터 타입에서 옵셔널 이름 뒤에 느낌표(!)를 두어 값을 추출되게 한다.

var index: Int?

index = 3

var treeArray = ["Oak", "Pine", "Yew", "Birch"]

if index != nil {
    //index 변수는 값이 할당되어 있다.
    print(treeArray[index?])
} else {
    //index 변수는 값이 할당되어있지 않다.
}
---------------------------------------
옵셔널 바인딩

if let constantname = optionalName {

}

if var variablename = optionalName {

}

위처럼 사용할 수 있는데, 이것을 이전 예제에서 강제 언래핑하던 방식을 바꿔보면 
----------------------------------------
var index: Int?

index = 3

var treeArray = ["Oak", "Pine", "Yew", "Birch"]

if let index {
    print(treeArray[indes])
} else {
    //index 변수는 값이 할당되어있지 않다.
}
----------------------------------------
var pet1: String?
var pet2: String?

pet1 = "Cat"
pet2 = "Dog"

if let pet1, let pet2 {
    print(pet1)
    print(pet2)
}
else {
    print("insufficient pets")
}

