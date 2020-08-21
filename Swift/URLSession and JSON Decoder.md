
```
let urlString = "http://xxx.xxx"
guard let url = URL(string: urlString) else {
    return
}

let session = URLSession.shared
let dataTask = session.dataTask(with: url) { (data, response, error) in
    if(error == nil) {
        let jsonDecoder = JSONDecoder()
        do {
            let decodeData = try jsonDecoder.decode(DataModel.self, from: data!)
        } catch {
            print(error.localizedDescription)
        }
    } else {
        print("error : " + error.debugDescription)
    }
}
```
