
##Codable
* Encodable과 Decodable 두 프로토콜을 모두 준수하는 타입
* User 타입은 서버에서 받은 JSON 데이터를 디코딩하거나, JSON 형태로 인코딩할 수 있다.

##Identifiable
* Identifiable 프로토콜을 준수하는 타입의 인스턴스는 id라는 속성을 통해 고유하게 식별될 수 있다,
* SwiftUI에서는 List 등에서 각 요소를 구분하기 위해 Identifiable 프로토콜을 활용한다.

```swift
struct User: Codable, Identifiable {
    var id: Int
    var login: String?
    var avatar_url: String?

    init(id: Int, login: String?, avatar_url: String?) {
        self.id = id
        self.login = login
        self.avatar_url = avatar_url
    }
}
```