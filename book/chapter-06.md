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
Khác với **if-else**, **switch** sẽ yêu cầu truyền các kiểu dữ liệu sau:

*   byte/Byte
*   short/Short
*   char/Character
*   int/Integer
*   Enumerated
*   String



Không như **if-else**, **switch** 

### Looping statements

#### for

#### for-each

#### while-do

#### do-while

### Branching statements

break, continue, return
