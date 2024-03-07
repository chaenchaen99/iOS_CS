##guard

guard 구문은 불리언 표현식을 포함, true 일 때만 guard 구문 다음에 위치한 코드가 실행된다.
guard 구문은 불리언 표현식이 false일 때 수행될 else절을 반드시 포함해야 한다.
else 절의 코드는 반드시 현재의 코드 흐름에서 빠져나가는 구문을 포함해야 한다.

func multiplyByTen(value: Int?) {
    guard let number = value, number < 10 else {
        print("Number is too high")
        return
    }

    let result = number * 10
    print(result)
}

multiplyByTen(value: 5)
multiplyByTen(value: 10)