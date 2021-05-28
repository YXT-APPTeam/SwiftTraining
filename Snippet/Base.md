# 基础题

## 基础知识问答

### Array

- 下面哪一行代码创建的是数组：

```swift
// 1:
let height = "14.0"

// 2:
var temperatures = [32.0]
```

- 下面哪一行代码创建的是数组：

```swift
1.
A:
var averages = [98.5, 97.1, 99.9]
B:
let status = false, true, true, true

2.
A:
var cities: [String] = ["London", "Paris", "New York"]
B:
let playlistSizes = (100, 200, 300)
```

- 下面哪一行代码创建的是数组：

```swift
1.
A:
let characters: [Int] = ["Doctor Who"]
B:
var readings: [Bool] = [false, false, true, false]

2.
A:
var scores: [Int] = [10, 12, 9]
B:
let breeds = {"Labrador", "Chihuahua"}

3.
A:
var singers = ["Taylor", "Adele", "Justin"]
B:
let age = 26
```

- 使用 Swift 的数组类型改写以下 Objective-C 代码：

```objective-c
1.
NSArray *windows = [[UIApplication sharedApplication] windows];

2.
// AVAsset *asset = ... // 此句不用改写
NSArray *videoTracks = [asset tracksWithMediaType:AVMediaTypeVideo];

3.
NSMutableArray *compQuaArr = [NSMutableArray array];
```

- 生成以下数组符合条件的子集：

```swift
1. 所有值大于 30 的元素：
let nums = [10,20,30,35,5,60]

2. 所有长度大于 4 个字符的名字，并且按字母表顺序排序首字母：
let names = ["Jobs", "Mikes", "Bob", "Abrahams", "Bruce", "Jeannette"]

3. 所有无法被 2 整除的元素，获取这些元素被 2 除的余数集合：
let nums = [2,4,7,9,3,13,18,22]
```

### Set

- 以下哪些行代码将创建一个包含 2 个元素的 set：

```swift
 1: var readings = Set([true, false, true, true])
 2: var attendees = Set([100, 100, 101, 100])
 3: let users = ["Taylor", "Adele"]
 4: let earthquakeStrengths = Set(1, 1, 2, 2)
 5: let cats = ["Burmese", "Siamese", "Persian"]
 6: var names = Set(["Sean", "Paul"])
 7: var colors = Set(["Red", "Green", "Red"])
 8: let staffReviews = Set([1, 2, 1, 2, 3])
 9: var ratings = Set([1, 1, 1, 2, 2, 2])
10: let playlistSizes = Set([1000])
11: var scores = Set([9, 10])
12: let averageHeights = Set([1.71, 1.72, 1.73])
```

### Array / Set 混合题

- 下面哪一项最适合使用数组存储：

```swift
1.用户地址
2.聊天程序中的消息
```

- 下面哪一项最适合使用数组存储：

```swift
1.拼字游戏中的单词表
2.未来 10 天的天气预报
```

- 下面哪一项最适合使用数组存储：

```swift
1.一首诗中的行
2.用户是否登录的标志
```

- 下面哪一项最适合使用数组存储：

```swift
1.专辑中的歌
2.现在的温度
```

- 下面哪一项最适合使用数组存储：

```swift
1.小孩每月量的身高
2.微博上所有用户名的列表
```

- 下面哪一项最适合使用数组存储：

```swift
1.游戏中的高分列表
2.一个人的姓名
```

### Tuples

- 请选择对 tuples 描述正确的项：

```swift
1.
A. 元组必须以变量的形式创建
B. 可以对元组中的元素命名
2.
A. 可以通过数字位置获取元组中的值
B. 元组中的所有值都必须不相同
3.
A. 元组不能包含多行字符串
B. 元组在圆括号中放置元素
4.
A. 不能改变元组中元素的类型
B. 元组只能包含字符串
5.
A. 元组大小是确定的
B. 元组和数组是相同的
```

### Dictionary

- 以下哪一行代码创建了一个字典：

```swift
1.
A:
var roles = ["captain": "Mal", "engineer": "Kaylee"]
B:
var place = ["road", "Park Lane", "city", "Cardiff"]

2.
A:
let location = ("road": "Park Lane", "city": "Cardiff")
B:
let heights = ["Taylor Swift": 1.78]

3.
A:
var address = ["road": "Park Lane", "city": "Cardiff"]
B:
var books = ["The Jungle Book"]

4.
A:
var speed = 60.75
B:
var capitals = ["England": "London", "Scotland": "Edinburgh"]

5.
A:
let forecast = ["Monday": "sunny", "Tuesday": "cloudy"]
B:
let isVisible = true

6.
A:
let scores = ["Sophie": 100]
B:
let password = "fr0sti3s"
```

- 以下代码是否有效：

```swift
1.
let ships = ["Star Trek", "Enterprise"]
let enterprise = ships["Star Trek"]

2.
let planets = [1: "Mercury", 2: "Venus"]
let venus = planets[2, default: "Planet X"]

3.
let ratings = [1: "Bad", 2: "OK", 3: "Good"]
let rating = ratings["2"]

4.
let capitals = ["England": "London", "Wales": "Cardiff"]
let scotlandCapital = capitals["Scotland"]

5.
let olympics = [2012: "London", 2016: "Rio", 2020: "Tokyo"]
let london = olympics[2012]

6.
let users = ["Taylor", "Taylor Swift"]
let taylor = users["Taylor", default: "Anonymous"]

7.
let books = ["Austen": "Pride and Prejudice"]
let dickens = books["Dickens", default: "Unknown"]

8.
let prices = ["Milk": 1, "Pepsi": 2]
let first = prices[0]

9.
let albums = ["Prince": "Purple Rain"]
let beatles = albums["Beatles"]

10.
let abbreviations = ["m": "meters", "km": "kilometers"]
let meters = abbreviations["m", default "m"]

11.
let characters = ["Captain": "Malcolm", "Engineer": "Kaylee"]
let captain = characters["Captain"]

12.
let scores = ["Paul": 80, "Sophie": 100]
let john = scores[john]
```

### 集合

- 下面哪一行代码是有效的：

```swift
1.
A:
var favoriteColors = Dictionary<String, String>()
B:
var measurements = [Double]

2.
A:
var states = Set<String>()
B:
var episodeNames = Array()

3.
A:
var answers = [Bool]()
B:
var badges = Set<>()

4.
A:
var scores = Array<Int>()
B:
var wines = Dictionary<String: String>()

5.
A:
var temperatures = [Double]()
B:
var mountainHeights = [String, Int]()

6.
A:
var friends = Set[String]()
B:
var authorAges = [String: Int]()
```

### 枚举

- 下面哪一项最适合使用枚举：

```swift
1.
A:
方向（东西南北）
B:
一系列物体的高度

2.
A:
旅游过的城市清单
B:
错误类型

3.
A:
电影类型
B:
一个邮箱地址

4.
A:
考试平均分
B:
一副纸牌中的花色

5.
A:
一年中的月份
B:
密码

6.
A:
星期
B:

```

- 以下哪一项创建的是带关联值的枚举：

```swift
1.
A:
enum Building { case skyscraper(floors: Int) }
B:
enum role { case administrator }

2.
A:
enum Sport { case running(distance: Int) }
B:
enum Status { case read }

3.
A:
let furniture = [chair, table, couch]
B:
enum CharacterClass { case paladin(level: Int) }

4.
A:
let chosenHobby = case hobby(name: String) }
B:
enum Instruments { case piano(isElectric: Bool) }

5.
A:
enum Forecast { case cloudy(coverage: Int) }
B:
enum SocialMedia case twitter(username: Int)

6.
A:
enum Activity { case reading(bookTitle: String) }
B:
case BandMember(role: String)
```





## 简单代码实现



- 请创建一个常量与可读写变量
- 将一个字符串进行二进制 UTF-8 编码。
- 打印一个包含当前系统时间的语句。
- 编写一个包含加、减、乘、除、取余、这 5 个运算的表达式。
- 创建一个函数，计算圆的周长，并将结果转换为整型值。
- 创建一个结构体，描述一杯咖啡（容量、口味、价格、含水量、咖啡因含量）。
- 创建一个协议，描述一家咖啡店的日常活动（制作咖啡、售卖咖啡、咖啡外送）。
- 创建一个类，描述一家零售店，并使用前一个咖啡经营的协议，实现咖啡经营相关的活动。