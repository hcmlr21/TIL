#ImagePicker

Assign UIImagePickerControllerDelegate

### CODE
```
let imagePicker = UIImagePickerController()
imagePicker.delegate = self
imagePicker.allowsEditing = true
imagePicker.sourceType = UIImagePickerController.SourceType.photoLibrary
        
self.present(imagePicker, animated: true, completion: nil)
```

```
// After image is chosen
func imagePickerController(_ picker: UIImagePickerController, didFinishPickingMediaWithInfo info: [UIImagePickerController.InfoKey : Any]) {
        self.imageView.image = info[UIImagePickerController.InfoKey.originalImage] as! UIImage
        
        dismiss(animated: true, completion: nil)
}
```
