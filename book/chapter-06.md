# Control Flow Statements

Ngoài những Operators thì Control Flow statements là thành phần không thể thiếu của các ngôn ngữ lập trình. Chúng bao gồm 3 nhóm chính: Decision-making, Looping và Branching

### Decision-making statements

Decision-making statements sẽ dựa vào một điều kiện sau đó quyết định sẽ thực hiện phần code nào.  
Một câu lệnh sẽ bao gồm 2 phần
*   Điều kiện
*   Phần code sẽ thực hiện
Mỗi câu lệnh có thể có liên kết nhiều điều kiện và nhiều phần code khác nhau cho mỗi điều kiện. Phần điều kiện là bắt buộc nhưng phần code có thể không có, nhưng như thế thì hơi vô nghĩa.  
Phần điều kiện bắt buộc phải là một biểu thức trả về kiểu dữ liệu boolean. Ví dụ
```java
var age = 22;
if (age >= 18) {
    System.out.println("Please come in");
}
```
Code dưới đây sẽ lỗi, do không phải kiểu boolean
```java
var adultFlag = 1;
if (adultFlag) { // không chấp nhận giá trị kiểu int
    System.out.println("Please come in");
}
```
Bạn cũng có thể gán giá trị cho biến trong điều kiện, miễn là nó trả về boolean
```java
var adult = false;
if (adult = checkAdult(22)) {
    System.out.println("Please come in");
}

// Method
public boolean checkAdult(int age) {
    return age >= 18;
}
```
Điều kiện của if chấp nhận kiểu Boolean, nhưng nếu nó mang giá trị **null**, *java.lang.NullPointerException* sẽ bị thrown ra
```java
Boolean adultFlag = null;
if (adultFlag) { // java.lang.NullPointerException
    System.out.println("Please come in");
}
```
Dấu ngoặc nhọn {} là không bắt buộc nếu bạn chỉ có một câu lệnh
```java
if (age >= 18) System.out.println("Please come in");
```
hoặc 
```java
if (age >= 18)
    System.out.println("Please come in");
```
Nhưng nếu viết như sau
```java
if (age >= 18)
    System.out.println("Please come in");
    System.out.println("Turn right");
```
sẽ mang nghĩa hoàn toàn khác so với
```java
if (age >= 18) {
    System.out.println("Please come in");
    System.out.println("Turn right");
}
```

#### if-then-else Statement

**else** là một cách để thêm đoạn code cần thực hiện nếu điều kiện trong **if** không thỏa mãn
```java
if (age >= 18) {
    System.out.println("Please come in");
} else {
    System.out.println("You are not allowed here");
}
```
Câu lệnh trên có nghĩa là nếu age lớn hơn hoặc bằng 18 sẽ in ra *Please come in*, nếu age không lớn hơn hoặc bằng 18, hay nói cách khác age nhỏ hơn 18, sẽ in ra *You are not allowed here*  
Cũng giống trường hợp trên, dấu ngoặc nhọn {} có thể bỏ nếu bạn chỉ có một câu lệnh
```java
if (age >= 18)
    System.out.println("Please come in");
else
    System.out.println("You are not allowed here");
```
else phải đi kèm với if, nếu không sẽ lỗi. Ví dụ:
```java
if (age >= 18)
    System.out.println("Please come in");
    System.out.println("Turn right");
else
    System.out.println("You are not allowed here");
```
Đoạn trên sẽ lỗi do câu lệnh if đã kết thúc trước đó và else không còn if đi kèm. Đây là Java, không phải Python.  
Bạn có thể không cần thực hiện gì sau if như dưới đây, dù không nên làm vậy
```java
if (age >= 18) {
    
} else {
    System.out.println("You are not allowed here");
}
```
Nhưng viết như dưới đây sẽ lỗi
```java
if (age >= 18)
else {
    System.out.println("You are not allowed here");
}
```
#### if-then-else-if Statement

Nhiều khi bạn có nhiều hơn hai điều kiện, bạn có thể có nhiều câu lệnh if-then hoặc thêm điều kiện if vào if-then-else
```java
if (age >= 18) {
    System.out.println("Please come in");
} else if (age >= 16) {
    System.out.println("You should not be here");
} else {
    System.out.println("You are not allowed here");
}
```
đoạn else cuối là không bắt buộc. Bạn có thể viết
```java
if (age >= 18) {
    System.out.println("Please come in");
} else if (age >= 16) {
    System.out.println("You should not be here");
}
```
Bạn có thể dùng nhiều lần **else-if**

#### switch Statement

**if-else** cũng hay, nhưng nếu viết quá nhiều sẽ gây rối và dễ nhầm lẫn. Trường hợp này thì nên dùng **switch**  
Ví dụ
```java
switch (month) {
    case 1: System.out.println("It's January");
        break;
    case 2: System.out.println("It's February");
        break;
    case 3: System.out.println("It's March");
        break;
    case 4: System.out.println("It's April");
        break;
    default: System.out.println("It doesn't matter");
        break;
}
```
Câu trên nếu dùng **if-else** sẽ như sau:
```java
if (month == 1) {
    System.out.println("It's January");
} else if (month == 2){
    System.out.println("It's February");
} else if (month == 3){
    System.out.println("It's March");
} else if (month == 4){
    System.out.println("It's April");
} else {
    System.out.println("It doesn't matter");
}
```
**switch** statement sẽ bao gồm:

*   switch và giá trị cơ sở
*   Các **case** và giá trị so sánh
*   **default** case
*   Các block code sẽ thực hiện tương ứng với các **case**

```java
int month = 1;
switch (month) { // month là giá trị cơ sở
    case 1: // case, so sánh month == 1
        // sẽ thực hiện nếu month == 1
        System.out.println("It's January");
        break;
    case 2: // case, so sánh month == 2
        // sẽ thực hiện nếu month == 2
        System.out.println("It's February");
        break;
    default: // default case, không có điều kiện
        // sẽ thực hiện nếu các case còn lại không khớp
        System.out.println("It doesn't matter");
        break;
}
```

Khác với **if-else**, **switch** sẽ yêu cầu truyền các kiểu dữ liệu sau:

*   byte/Byte
*   short/Short
*   char/Character
*   int/Integer
*   Enumerated
*   String

Nếu truyền vào **null**, tương tự như **if-else**, lỗi *java.lang.NullPointerException* sẽ bị thrown ra
```java
String month = null;
switch (month) { // java.lang.NullPointerException
...
}
```
Giá trị tĩnh trong **switch** cũng được chấp nhận
```java
switch (1) {
    case 1:
        break;
    case 2:
        break;
}
```
Kiểu dữ liệu ở **case** phải tương ứng với **switch**  
Viết như dưới đây sẽ sai
```java
String month = "1";
switch (month) { // month kiểu String
    case 1: // case kiểu int
        break;
    
}
```
nhưng với Wrapper Class tương ứng thì được chấp nhận
```java
Integer month = 1;
switch (month) { // month kiểu Integer
    case 1: // case kiểu int
        break;
    
}
```
Giá trị ở **case** không được *null* và phải là một giá trị tĩnh  
Những đoạn dưới đây sẽ lỗi
```java
var actualMonth = 1;
switch (month) {
    case actualMonth: // lỗi Constant expression required
        break;
    
}
```
tương tự
```java
switch (month) {
    case getMonth(): // lỗi Constant expression required
        break;
    
}
```
Tương tự như dùng method, khởi tạo giá trị bằng từ khóa **new** cũng không được coi là giá trị tĩnh
```java
switch (month) {
    case new String("1"): // lỗi do dùng new để khởi tạo
        break;
    
}
```
không được **null**
```java
switch (month) {
    case null: // lỗi
        break;
    
}
```
Expression được chấp nhận, nhưng cũng phải là các giá trị tĩnh
```java
switch (time) {
    case 60*60:
        break;
}
```java
var minute2Second = 60;
switch (time) {
    case 60*minute2Second: // lỗi do có biến minute2Second
        break;
}
```
Biến **final** cũng có thể là giá trị tĩnh nếu javac có thể tính toán được giá trị thực của biến khi compile  
```java
final var minute2Second = 60;
switch (time) {
    case minute2Second: // không lỗi do minute2Second là final
        break;
    case 60*minute2Second: // không lỗi
        break;
}
```
```java
final var minute2Second = getMonth();
switch (time) {
    case minute2Second: // lỗi. Không thể biết getMonth() trả về gì khi compile
        break;
}
```
hoặc
```java
final var minute2Second = new Integer(60);
switch (time) {
    case minute2Second: // lỗi. new Integer(60) cũng không phải giá trị tĩnh
        break;
}
```
tương tự
```java
final var minute2Second = Integer.valueOf(60);
switch (time) {
    case minute2Second: // lỗi. Integer.valueOf(60) không phải giá trị tĩnh
        break;
}
```
Ví dụ đoạn code sau
```java
final Integer minute2Second = 60;
switch (time) {
    case minute2Second: // lỗi
        break;
}
```
đoạn code trên lỗi vì với Java
```java
final Integer minute2Second = 60;
```
tương đương với
```java
final Integer minute2Second = Integer.valueOf(60);
```

Với **if-else**, bạn có thể sử dụng nhiều điều kiện **if** giống nhau (dù vô nghĩa). Nhưng với **switch**, các **case** không được phép giống nhau
```java
switch (month) {
    case 1: 
        break;
    case 1: // lỗi duplicate case label
        break;
}
```
```java
final var january = 1;
switch (month) {
    case 1: 
        break;
    case january: // lỗi duplicate case label
        break;
}
```
```java
final var january = 1;
switch (month) {
    case 2: 
        break;
    case january + 1: // lỗi duplicate case label
        break;
}
```

**default** là một **case** đặc biệt, tương tự như **else**, khi các giá trị **case** không được khớp thì block code của **default** sẽ được chạy  
```java
var month = 11;
switch (month) {
    case 1:
        System.out.println("It's January");
        break;
    case 2:
        System.out.println("It's February");
        break;
    default:
        System.out.println("Nevermind");
        break;
}
```
In ra *Nevermind* do cả 2 **case** đều không khớp  

Những câu lệnh để kết thúc mỗi **case** và ra khỏi **switch** như **break**, **return** và **throw** là rất quan trọng để **switch** có thể ra kết quả mong muốn. Ta đã biết là block code trong **case** hoặc **default** sẽ được chạy nếu khớp. Tuy nhiên, nếu trong block code đó không có câu lệnh **break**, **return** hoặc **throw**, cả những block code của case phía dưới cũng sẽ được chạy cho đến khi gặp câu lệnh **break**, **return** hoặc **throw**.   
Xem ví dụ sau
```java
var month = 1;
switch (month) {
    case 1:
        System.out.println("It's January");
        // Không có break
    case 2:
        System.out.println("It's February");
        break;
    default:
        System.out.println("Nevermind");
        // Không có break
}
```
In ra
```txt
It's January
It's February
```
hoặc
```java
var month = 2;
switch (month) {
    case 1:
        System.out.println("It's January");
        // Không có break
    case 2:
        System.out.println("It's February");
        // Không có break
    default:
        System.out.println("Nevermind");
        // Không có break
}
```
In ra
```txt
It's February
Nevermind
```

Nếu đặt **default** lên trên
```java
var month = 3;
switch (month) {
    default:
        System.out.println("Nevermind");
        // Không có break
    case 1:
        System.out.println("It's January");
        // Không có break
    case 2:
        System.out.println("It's February");
        // Không có break
}
```
In ra
```txt
Nevermind
It's January
It's February
```
Thứ tự của các câu lệnh **case** và **default** không phải bắt buộc và cũng không ảnh hưởng gì đến tốc độ xử lý. Nhưng khuyến khích đặt các **case** có giá trị từ thấp đến cao và **default** ở cuối cùng. Câu lệnh **break**/**return** ở **case** hoặc **default** cuối đôi khi không mang nhiều ý nghĩa, nhưng nên đặt để tránh lỗi không mong muốn.

Khi dùng với kiểu **enum**,  tên **enum** không nhất thiết cần đi theo giá trị  

Ví dụ khi gọi một giá trị enum, ta thường dùng kèm với tên enum (nếu không **import static**)
```java
if (month == Month.JANUARY) {
    ...
}
```
Nhưng nếu là **switch**, tên **enum** lại không phải bắt buộc
```java
enum Month {
    JANUARY, FEBRUARY
}
...
var month = Month.FEBRUARY;
switch(month) {
    case JANUARY: // không cần Month.JANUARY
        break;
    case FEBRUARY: // không cần Month.FEBRUARY
        break;
}
```
Cách java so sánh giữa giá trị cơ sở tại **switch** với giá trị ở các **case** cũng linh hoạt tùy theo kiểu dữ liệu  

Với kiểu **primitive data**, biểu thức so sánh bằng (==) sẽ được dùng.  

Với **Wrapper class**, biến trong **switch** sẽ được **unboxing** trước, sau đó dùng biểu thức so sánh bằng (==) để so sánh
```java
Integer month = 2;
switch (month) {
    case 1: break;
    case 2: break;
}
```
sẽ được đổi thành
```java
Integer month = 2;
switch (month.intValue()) {
    case 1: break;
    case 2: break;
}
```
tương tự với các kiểu khác
```java
Byte month = 2;
switch (month.byteValue()) {
    case 1: break;
    case 2: break;
}
```
Với **String**, method **equals** sẽ được dùng
```java
String month = new String("january"); // không nên dùng new String(<value>) trong thực tế
switch (month) {
    case "january": break; // diễn giải thành month.equals("january")
    case "february": break; // diễn giải thành month.equals("february")
}
```
Với **enum**, biến trong **switch** sẽ được chuyển sang ordinal trước, sau đó dùng biểu thức so sánh bằng (==) để so sánh ordinal với các **case**
```java
enum Month {
    JANUARY, FEBRUARY
}
...
var month = Month.FEBRUARY;
switch(month) {
    case JANUARY:
        break;
    case FEBRUARY:
        break;
}
```
sẽ tương đương
```java
switch(month.ordinal()) {
    case 1: // compiler tự động convert từ JANUARY sang ordinal là 1
        break;
    case 2: // compiler tự động convert từ FEBRUARY sang ordinal là 2
        break;
}
```

**switch statements** được thay đổi khá nhiều trên những phiên bản Java cao hơn như chấp nhận **null**, biểu thức so sánh (thay vì giá trị tĩnh).

### Looping statements

#### for

#### for-each

#### while-do

#### do-while

### Branching statements

break, continue, return
