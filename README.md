# URL-Safe Base64 encoding in Swift
This repository provides a class file for easy and fast encoding and decoding with standard Base64. It removes the "/" and "+" characters from the standard Base64 implementation and replaces them with "-" and "_" as decribed by the 'base64url' standard.

Copy the class file into your project and call it directly to use it.

## Encoding Data

The data provided to the function must be an array of UInt8. There is a built in initiliser to turn a Data object into this form.

```swift
let data: [UInt8] = [1, 2, 3]
let encodedData = Base64FS.encode(data: data)
```

or

```swift
let data: Data = ...
let dataInCorrectFormat = [UInt8](data)
let encodedData = Base64FS.encode(data: dataInCorrectFormat)
```

## Encoding Strings

For common use cases with filenames and URLs, you can use a string method directly as shown:

```swift
let str = "Hello, World"
let encodedString = Base64FS.encodeString(str: str)
```


## Decoding

In an almost identical fasion to the two previous examples, you use the following two functions:


#### Data
```swift
let encodedData = ...
let encodedDataInCorrectFormat  = [UInt8](encodedData)
let decodedData = Base64FS.decode(data: encodedDataInCorrectFormat)
```

#### String
```swift
let encodedStr = ...
let decodedString = Base64FS.decodeString(str: encodedStr)
```



