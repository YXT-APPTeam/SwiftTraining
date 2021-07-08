- 编写一个方法，计算在星巴克点若干杯咖啡该付多少钱（最少点一杯），价格表参考：
  - 中杯：¥28
  - 大杯：¥32
  - 超大杯：¥38

- 创建一个协议，表示商品的价目信息（条码值、单价），使用这个协议编写一个收银方法，用于超市结账时根据扫码结果计算总价。

- 有以下两个类型，它们的内存占用大小分别是多少？

```swift
enum AlgorithmType: String {
    case quickSort
    case mergeSort
}

struct AlgorithmItem {
    var type: AlgorithmType
    var name: String
}
```

- 以下两个类型的内存占用大小是否相同：

```swift
struct AlgorithmItem {
    var type: AlgorithmType
    var name: String
}

struct AlgorithmItem2 {
    var name: String
    var type: AlgorithmType
}
```
