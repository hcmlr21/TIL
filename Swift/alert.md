# alert

### code

```
let alert = UIAlertController(title: "title", message: "message", preferredStyle: .alert)
alert.addAction(UIAlertAction(title: "OK", style: .default, handler: { (action) in
    exit(0) //Exit App
}))
            
self.present(alert, animated: true, completion: nil)
```
