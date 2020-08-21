# Codable : EnCodable & DeCodable

### Protocol

'''
struct Person: Codable {
    var name: String?
    var age: Int?
    var birthDay: String?
    
    enum CondingKeys: String, CodingKey {
        case name, age
        case birthDay = "birth_day"
    }
}
'''
