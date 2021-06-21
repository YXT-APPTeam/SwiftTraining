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

- 编写代码生成符合以下条件的数组子集：

```swift
1. 所有值大于 30 的元素：
let nums = [10,20,30,35,5,60]

2. 所有长度大于 4 个字符的名字，并且按字母表顺序排序首字母：
let names = ["Jobs", "Mikes", "Bob", "Abrahams", "Bruce", "Jeannette"]

3. 所有无法被 2 整除的元素，获取这些元素被 2 除的余数集合：
let nums = [2,4,7,9,3,13,18,22]

4. 使用 reduce 方法重写第 1、3 题。(评分标准：10 行内实现的 90 分，6 行内实现的满分 100 分，1 行内实现的 110 分)。

// 参考答案：
1. nums.filter { $0 > 30 }
2. names.filter { $0.count > 4 }.sorted(by: <)
3. nums.filter { $0 % 2 != 0 }.map { $0 % 2 }
4. 
let numsLargerThan30 = nums.reduce([Int]()) { $1 > 30 ? $0 + [$1] : $0 }
let numsCannotDivideBy2 = nums2.reduce([Int]()) { $1 % 2 > 0 ? $0 + [$1 % 2] : $0 }
```

- 给 Array 类型添加扩展方法，用于给数组扩容，执行条件：当数组中现有元素数量超过当前容量一半时扩容（容量翻倍）；另外，如果数组元素是 String 类型时，扩容时容量变为原来 3 倍。

```swift
// 参考答案
extension Array {
    func shouldAddCapacity() -> Bool {
        guard count > capacity / 2 else { return false }
        return true
    }
    
    mutating func addCapacity() {
        guard shouldAddCapacity() else { return }
        reserveCapacity(capacity * 2)
    }
}

extension Array where Element == String {
    mutating func addCapacity() {
        guard shouldAddCapacity() else { return }
        reserveCapacity(capacity * 3)
    }
}
```

### 字符串

- 哪一行代码创建的是字符串：

```swift
1.
A:
var mortgageRemaining = 100_000
B:
var dogBreed = "samoyed"

2.
A:
var speed = 88
B:
var age = "23"

3.
A:
var repeatCount = 82
B:
var selectedWood = "mahogany"

4.
A:
var highScore = 328_556
B:
var sizeInInches = "27"

5.
A:
var currentSong = "Rainbow to the Stars"
B:
var power = 9001

6.
A:
var winner = "Miguel"
B:
var rating = 5
```

- 以下代码创建的多行字符串是否正确：

```swift
1.
var burns = """
The best laid schemes
o' mice an' men
gang aft agley
"""

2.
var shakespeare = """
To be or not to be
that is the question
"""

3.
var joseph = """
When I am an old woman,
I shall wear purple
with a red hat that doesn't go,
and doesn't suit me
"""

4.
var eliot = "This is the way the world ends
Not with a bang but with a whimper"

5.
var tennyson = """
Tis better to have loved
and lost than never
 to have loved at all
"""

6.
var lear = "The Owl and the Pussy-cat went to sea
In a beautiful pea-green boat,
They took some honey, and plenty of money,
Wrapped up in a five-pound note."

7.
var wordsworth = """
I wandered lonely as a cloud
that floats on high
o'er vales and hills
"""

8.
var coleridge = """
Water, water, everywhere
and not a drop to drink"""

9.
var henley = """I am the master of my fate
I am the captain of my soul"""

10.
var rossetti = """
For if the darkness and corruption leave
A vestige of the thoughts that once I had,
Better by far you should forget and smile
Than that you should remember and be sad.
"""

11.
var shelley = "My name is Ozymandias, King of Kings
Look on my works, ye mighty, and despair!"

12.
var brooke = ""If I should die,
think only this of me
There is some corner of a foreign field
That is forever England."
```

- 以下哪一行代码使用了字符串插值：

```swift
1.
A:
var name = "\(firstName) \(lastName)"
B:
var versionString = "You're using v(version)"

2.
A:
var alert = "Error: \(message)!"
B:
var message = "Installation failed: \{reason}."

3.
A:
var forecast = "Today's weather will be \(weather)"
B:
var formattedHeight = "You are (size)cm"

4.
A:
var result = "\(daysRemaining) days to go"
B:
var engine = "Your engine is (size)cc"

5.
A:
var str = "Hello, playground!"
B:
var warning = "You need to be \(years) or older"

6.
A:
var error = "Error, please try again."
B:
var greeting = "Hello, \(name)!"
```

- 使用 Swift 改写以下 Objective-C 代码：

```swift
1.
NSString * videoPath = [NSSearchPathForDirectoriesInDomains(NSDocumentDirectory, NSUserDomainMask, YES).firstObject stringByAppendingString:@"/cutVideo.mp4"];

2.
NSTimeInterval timeInterval = [[NSDate date] timeIntervalSince1970];
NSString * fileName = [NSString stringWithFormat:@"PHMediaAudioRecorder_%.0f.mp3",timeInterval];

3.
NSString *httpStr = @"http://yxt.yunxuetang.cn";
if ([httpStr hasPrefix:@"http://"]) {
  return YES;
}

4.
NSString *keyPath = @"status";
if ([keyPath isEqualToString:@"status"]) {
}
```

- 编写一个方法判断一个字符串是否全部为不重复的字符（区分大小写）。
- 编写一个方法判断一个字符串是否为回文体(正向和反向读一样)，如：'rotator' 正确，'note eton' 正确，'ne rren' 错误（空格未匹配），（忽略大小写）。

### 函数

- 以下代码是否正确：

```swift
1.
func recordPodcast(name: String, length: Int) {
	if length > 60 {
		print("That's too long!")
	} else {
		print("Recording \(name)...")
	}
}

2.
func driveCar(_ type: String) {
	print("I'm test driving a \(type)")
}
driveCar("Ferrari")

3.
func play(games: String...) {
	for game in games {
		print("Let's play \(game)!")
	}
}
play(games: "Chess")

4.
func makeSandwich(fillings String...) {
	print("I'm making a sandwich...")
	for filling in fillings {
		print("Let's add some \(filling).")
	}
}

5.
enum ReadingErrors: Error {
	case tooBoring
}
func readBook(isFiction: Bool = true) throws {
	if isFiction {
		print("Story time!")
	} else {
		throw ReadingErrors.tooBoring
	}
}

6.
enum SwimmingError: Error {
	case cantSwim
}
func swim(distance: Int) {
	throw SwimmingError.cantSwim
}

7.
func sumOfFactors(for number: Int) -> Int {
	var sum = 0
	for i in 1...number {
		if number % i == 0 {
			sum += i
		}
	}
	return sum
}
let sum = sumOfFactors(for: 100)

8.
func eatIceCream {
	print("Yum!")
}

9.
func checkFor(_ searchName: String, in names: [String]) -> Bool {
	for name in names {
		if name == searchName {
			return true
		}
	}
}

10.
func showStartPrompt() {
	print("Tap the screen to begin")
}

11.
func isUserAllowed(name username: String) -> Bool {
	if name == "Anonymous" {
		print("Forbidden")
	} else {
		print("Allowed")
	}
}

12.
func paintWalls(tastefully: Bool, color: inout String) {
	if tastefully {
		color = "cream"
	} else {
		color = "tartan"
	}
}
let color = ""
paintWalls(tastefully: true, color: &color)
```

### 闭包

- 以下代码是否正确：

```swift
1.
var signAutograph(to name: String) = {
	print("To \(name), my #1 fan")
}
signAutograph(to: "Lisa")

2.
var paintPicture() {
	print("Where are my watercolors?")
}

3.
let learnSwift = {
	print("Closures are like functions")
}
learnSwift()

4.
let greetUser = {
	print("Hi there!")
}
greetUser()

5.
var connectVPN = {
	print("Connected!")
}
connectVPN()

6.
takeCruise = {
	print("A week of vacation!")
}

7.
let sing {
	print("Tralala")
}
sing()

8.
var meetFriends = {
	print("Let's watch a movie")
}
meetfriends()

9.
let walkDog = {
	print("Let's go to the park")
}

10.
let upgrade() = {
	print("Upgrading...")
}
upgrade()

11.
var castVote = {
	print("I voted!")
}
castVote()

12.
var takeMedicine = {
	print("I feel a little better")
}
```

- 以下代码是否正确：

```swift
1.
var cleanRoom = { (name: String) in
	print("I'm cleaning the \(name).")
}
cleanRoom("kitchen")

2.
var sendMessage = { (message: String) in
	if message != "" {
		print("Sending to Twitter: \(message)")
	} else {
		print("Your message was empty.")
	}
}

3.
var click = { (button: Int) in
	if button >= 0 {
		print("Button \(button) was clicked.")
	} else {
		print("That button doesn't exist.")
	}
}

4.
printDocument = { (copies: Int) in
	for _ in 1...copies {
		print("Printing document...")
	}
}

5.
var shareWinnings = { (amount: Double) in
	let half = amount / 2.0
	print("It's \(half) for me and \(half) for you.")
}
shareWinnings("50")

6.
var pickFruit = { (name: String) in
	switch name {
	case strawberry:
		fallthrough
	case raspberry:
		print("Strawberries and raspberries are half price!")
	default:
		print("We don't have those.")
	}
}

pickFruit("strawberry")

7.
let calculateResult = { (answer) in
	if answer == 42 {
		print("You're correct!")
	} else {
		print("Try again.")
	}
}

8.
let fixCar = { (problem: String) in
	print("I fixed the \(problem).")
}

9.
let makeReservation = { (people: Int) in
	print("I'd like a table for \(people), please.")
}

10.
var cutGrass = { (length currentLength: Double) in
	switch currentLength {
	case 0...1:
		print("That's too short")
	case 1...3:
		print("It's already the right length")
	default:
		print("That's perfect.")
	}
}

11.
let watchTV = { (channel: String) in
	print("I'm going to watch some \(channel)")
}
watch_TV("BBC News")

12.
let rowBoat = { (distance: Int) in
	for _ in 1...distance {
		print("I'm rowing 1km.")
	}
}
rowBoat(5)
```

- 以下代码是否正确：

```swift
1.
var flyDrone = { (hasPermit: Bool) -> Bool in
	if hasPermit {
		print("Let's find somewhere safe!")
		return true
	}
	print("That's against the law.")
	return false
}

2.
let shovelSnow = { (depth) -> String in
	if depth < 1 {
		return "OK, I can do this..."
	} else {
		return "I need some help!"
	}
}

3.
let measureSize = { (inches: Int) -> String in
	switch inches {
	case 0...26:
		return "XS"
	case 27...30:
		return "S"
	case 31...34:
		return "M"
	case 35...38:
		return "L"
	default:
		return "XL"
	}
}
measureSize(36)

4.
func callNumber = { (number: Int) -> String in
	return "Calling now..."
}

5.
let goSurfing = { (waveHeight: Int) in
	if waveHeight < 5 {
		return "Let's go!"
	} else if waveHeight < 10 {
		return "This could be tricky"
	} else if waveHeight < 20 {
		return "Only a pro could do that"
	} else {
		return "No way!"
	}
}

6.
var difficultyRating = { (trick: String) -> Int in
	if trick == "ollie" {
		return 1
	} else if trick == "Yoyo Plant" {
		return 3
	} else if trick == "900" {
		return 5
	} else {
		return 0
	}
}
print(difficultyRating("ollie"))

7.
let convertNumerals = { (numeral: String) -> String in
	switch numeral {
	case "I":
		return "1"
	case "II":
		return "2"
	case "III":
		return "3"
	}
}
print(convertNumerals("II"))

8.
var goToWork = { (hours: String) -> Bool in
	print("I'm going to work")
	for _ in 1...hours {
		print("I'm chatting to friends on Facebook.")
	}
	print("I'm going home")
	return true
}

9.
var costToShootMovie = { (location: String) -> Int in
	if location == "UK" {
		return 1_000_000
	} else if location == "US" {
		return 5_000_000
	} else {
		return 500_000
	}
}

10.
let writeEssay = { (topic: String) -> String in
	return "Here's an essay on \(topic)."
}

11.
var buyMagazine = { (name: String) -> Int in
	let amount = 10
	print("\(name) costs \(amount)")
	return amount
}
buyMagazine(name: "Wired")

12.
let bakeBirthdayCake = { (name: String) -> Int in
	print("I've made a cake for \(name); here's the bill.")
	return 50
}
```

- 以下代码是否正确：

```swift
1.
var swift {
	print("Cool - I can use closures!")
}
func writeCode(using language: () -> Void) {
	language()
	print("That'll be eleventy billion dollars, please.")
}

2.
var playWithDog = {
	print("Fetch!")
}
func play(using playType: () -> Void) -> String {
	print("Let's play a game")
	playType()
}
play(using: playWithDog)

3.
var makeFromStraw = {
	print("Let's build it out of straw")
}
func buildHouse(using buildingStyle: () -> Void) {
	buildingStyle
	print("It's ready - can anyone blow it down?")
}

4.
let awesomeTalk = {
	print("Here's a great talk!")
}
func deliverTalk(name: String, type: () -> Void) {
	print("My talk is called \(name)")
	type()
}
deliverTalk(name: "My Awesome Talk", type: awesomeTalk)

5.
let swanDive = {
	print("SWAN DIVE!")
}
func performDive(type dive: () -> Void) {
	print("I'm climbing up to the top")
	dive()
}
performDive(type: swanDive)

6.
let helicopterTravel = {
	print("Get to the chopper!")
}
func travel(by travelMeans: () -> Void) {
	print("Let's go on vacation...")
	travelMeans()
}
travel(by: helicopterTravel)

7.
let evilRobot = {
	print("EXTERMINATE")
}
func buildRobot(personality: () -> Void) {
	print("Time to turn on the robot!")
	personality()
}
buildRobot(using: evilRobot)

8.
var goOnBike = {
	print("I'll take my bicycle.")
}
func race(using vehicleType: () -> Void) {
	print("Let's race!")
	vehicleType()
}

9.
var payCash = {
	print("Here's the money.")
}
func buyClothes(item: String, using payment: () -> Void) {
	print("I'll take this \(item).")
	payment()
}
buyClothes(item: "jacket", using: payCash)

10.
var payCash = {
	print("Here's the money.")
}
func buyClothes(item: String, using payment: () -> Void) {
	print("I'll take this \(item).")
	payment()
}
buyClothes(item: "jacket", using: payCash)

11.
let driveSafely = {
	return "I'm being a considerate driver"
}
func drive(using driving: () -> Void) {
	print("Let's get in the car")
	driving()
	print("We're there!")
}
drive(using: driveSafely)

12.
var learnWithUnwrap = {
	print("Hey, this is fun!")
}
func learnSwift(using approach: () -> Void) {
	print("I'm learning Swift")
	approach()
}
learnSwift(using: learnWithUnwrap)
```

- 以下代码是否正确：

```swift
1.
func holdClass(name: String, lesson: () -> Void) {
	print("Welcome to \(name)!")
	lesson()
	print("Make sure your homework is done by next week.")
}
holdClass("Philosophy 101", lesson:) {
	print("All we are is dust in the wind, dude.")
}

2.
func phoneFriend(conversation: () -> Void) {
	print("Calling 555-1234...")
	conversation()
}
phoneFriend:
	print("Hello!")
	print("A foreign prince wants to give you $5 million.")
	print("What are your bank details?")

3.
func doTricks(_ tricks: () -> Void) {
	print("Start recording now!")
	tricks()
	print("Did you get all that?")
}

4.
func tendGarden(activities: () -> Void) {
	print("I love gardening")
	activities()
}
tendGarden {
	print("Let's grow some roses!")
}

5.
func makeCake(instructions: () -> Void) {
	print("Wash hands")
	print("Collect ingredients")
	instructions()
	print("Here's your cake!")
}
makeCake {
	print("Mix egg and flour")
}

6.
func brewTea(steps: ()) {
	print("Get tea")
	print("Get milk")
	print("Get sugar")
	steps()
}
brewTea {
	print("Brew tea in teapot.")
	print("Add milk to cup")
	print("Pour tea into cup")
	print("Add sugar to taste.")
}

7.
func assembleToy(instruction: () -> Void) {
	instructions()
	print("It's done!")
}
assembleToy {
	print("Grok the glib")
	print("Flop the flip")
	print("Click the clack")
}

8.
func knitSweater(then: () -> Void) {
	print("Buy wool")
	for _ in 1...100 {
		print("Knit knit knit...")
	}
	action()
}
knitSweater {
	print("Who wants to buy a sweater?")
}

9.
func repeatAction(count: Int, action: () -> Void) {
	for _ in 0..<count {
		action()
	}
}
repeatAction(count: 5) {
	print("Hello, world!")
}

10.
func clean(tasks: () -> Void) {
	print("It's time to clean the house.")
	tasks()
}
clean [
	print("I'm going to clean the kitchen.")
	print("I'm going to tidy the study.")
	print("I'm going to nuke the kids' room.")
]

11.
func goCamping(then action: () -> Void) {
	print("We're going camping!")
	action()
}
goCamping {
	print("Sing songs")
	print("Put up tent")
	print("Attempt to sleep")
}

12.
func goOnVacation(to destination: String, _ activities: () -> Void) {
	print("Packing bags...")
	print("Getting on plane to \(destination)...")
	activities()
	print("Time to go home!")
}
goOnVacation(to: "Mexico") {
	print("Go sightseeing")
	print("Relax in sun")
	print("Go hiking")
}
```

- 使用闭包语法改写以下 Objective-C 代码：

```swift
typedef void(^cutCompleteBlock)(NSString * _Nonnull videoPath, NSString * _Nonnull thumbnailPath);
@property (nonatomic, copy) cutCompleteBlock _Nullable completeBlock;

editorVC.completeBlock = ^(NSString * _Nonnull videoPath, NSString * _Nonnull thumbnailPath) {
    // 视频
    long long videoLength = [PHResourceChooseUtil getVideoTimeWithLocalPath:videoPath];
    long long videoSize = [[PHFileManager sizeOfFileAtPath:videoPath] longLongValue];
    pickerModel.fileVideoPath = videoPath;
    pickerModel.videoLength = videoLength;
    pickerModel.videoFileSize = videoSize;
    // 封面
    long long imageFileSize = [[PHFileManager sizeOfFileAtPath:thumbnailPath] longLongValue];
    pickerModel.fileImagePath = thumbnailPath;
    pickerModel.imageFileSize = imageFileSize;

    [weakSelf handleSelectedVideoWithPickerModel:pickerModel videoConfigModel:videoConfigModel];
};
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

- 以下哪一项关于枚举的 raw value 描述是正确的：

```swift
1.
A: raw value 让枚举转变成了字典
B: 每个 case 都可以指定 raw value

2.
A: Int 类型的 raw value 默认从 0 开始
B: 如果给一个 case 设置了 raw value 那么必须给所有 case 都设置

3.
A: 可以不使用 raw value
B: raw value 与关联值是一回事

4.
A: raw value 必须是字符串
B: raw value 可以使用 Int 类型值

5.
A: raw value 可以让我们动态创建枚举
B: raw value 不能直接使用

6.
A: raw value 可以让 case 具体一定含义
B: 枚举必须包含 raw value
```

### 协议

- 以下协议定义是否正确：

```swift
1.
protocol Swimmable {
	var depth { get }
}

2.
protocol Purchaseable {
	var price: Double { get set }
	var currency: String { get set }
}

3.
protocol Climbable {
	var height: Double { get }
	var gradient: Int { get }
}

4.
protocol Mailable {
	var width: Double { get, set }
	var height: Double { get, set }
}

5.
protocol Strokeable {
	fluffiness: Int { get }
}

6.
protocol Learnable {
	var difficulty: Int { get }
}

7.
protocol Washable {
	var dirtinessLevel: Int { get set }
}

8.
struct Knittable {
	var needleSizes: [Double] { get set }
}

9.
protocol Singable {
	var lyrics: [String] { get set }
	var notes: [String] { get set }
}

10.
protocol Plantable {
	var requirements: [String] { get set }
}

11.
protocol Buildable {
	var numberOfBricks: Int { set }
	var materials: [String] { set }
}

12.
protocol Liftable {
	var weight: Double get set
}
```



### 混合题

- 以下代码创建的是否为数组、字典、set、元组中的一种类型：

```swift
1. var fibonacci = (1, 1, 2, 3, 5, 8)
2. var repeatCount = [String: Int]
3. let usedWords = Set(["hello", "world"])
4. let winners: [String] = ("David", "Jason", "Raquel")
5. var lotteryNumbers = Set(11, 23, 44)
6. var names = ["Beyoncé", "Jay-Z"]
7. var unreadMessages: Int = "12"
8. let episodes = [String]()
9. var scores = [100, 90, 85]
10. let ages: Int = [26, 28, 39]
11. let credentials = ["username": "twostraws"]
12. let isConfigured = false
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