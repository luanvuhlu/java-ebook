# Kiểu dữ liệu

Java là ngôn ngữ có kiểu dữ liệu tĩnh (statically-typed), tức là tất cả các biến phải được khai báo kiểu dữ liệu (rõ ràng hoặc được ngầm hiểu) và không thể thay đổi sau này.
Trái ngược với statically-typed là dynamic-typed, nơi biến có thể được sử dụng trước cả khi khai báo. Kiểu dữ liệu cũng không cần khai báo và có thể được thay đổi tùy ý. Dynamic-typed mang lại sự tiện lợi cho người lập trình nhưng ngược lại rất dễ dẫn đến lỗi.

+++

Java nhấn mạnh vào tính hướng đối tượng, (gần như) mọi thứ đều là đối tượng, nhưng cũng như những ngôn ngữ lập trình thời bấy giờ, cụ thể là C/C++, Java vẫn giữ lại những kiểu dữ liệu không phải đối tượng, chính là kiểu dữ liệu nguyên thủy (Primitive Data Types)

### Primitive Data Types
Có ba nhóm kiểu dữ liệu nguyên thủy chính là Numeric, Character và Boolean.

#### Numeric Data Types
| Data type | Size                                          | Range                     | Default Value | Example                                                 |
|--------------|--------------------|-------------------------------------------------------------|----------------------------|-----------------------------------------------|
| byte      | 8-bit                                         | $-128$ ~ $127$              | 0                          | byte number = 0                                         |
| short     | 16-bit                                        | $-32768$ ~ $32767$            | 0                          | short number = 0                                        |
| int       | 32-bit                                        | $-2147483648$ ~ $2147483647$            | 0                          | int number = 0                                          |
| long      | 64-bit                                        | $-2^{63}$ ~ $2^{63}-1$            | 0L                         | long number = 0<br/>long number = 0L                        |
| float     | 32-bit | $-2^{149}$ ~ $(2-2^{-23})2^{127}$   | 0.0f                       | float number = 0  <br/>float number = 0f                      |
| double    | 64-bit | $-2^{1074}$ ~ $(2-2^{-52})2^{1023}$ | 0.0d                       | double number = 0  <br/>double number = 0f  <br/>double number = 0d |

#### Character Data Types

Char type here

#### Boolean Data Types

Boolean type here

> Fact: Có nhiều tranh cãi cho rằng Java không phải là ngôn ngữ thuần hướng đối tượng xoay quanh việc Java có kiểu dữ liệu nguyên thủy. Thật vậy, những biến có kiểu dữ liệu nguyên thủy không phải đối tượng, việc sử dụng nó đi ngược lại hoàn toàn nguyên tắc của lập trình hướng đối tượng.

### Một số điểm cần lưu ý với kiểu dữ liệu nguyên thủy trong Java

**Khi gán giá trị vượt quá độ lớn của kiểu dữ liệu, giá trị nhận được sẽ rất khó đoán**

Xem 2 ví dụ dưới đây:
```java
int num1 = 2147483648;
```
và
```java
int num1 = 2147483647;
int num2 = num1 * 100;
System.out.println(num2);
```
Ví dụ thứ nhất chắc chắn không thể compile và báo lỗi compile error ngay lập tức. Nhưng ở ví dụ thứ hai, không hề có lỗi nào xảy ra và kết quả ra lại rất bất ngờ (ít nhất là ở máy tôi), là -100.  
Đừng cố đoán giá trị trong các trường hợp này, vì dù gì gán như vậy cũng là điều không nên làm.

**Số nguyên mặc định sẽ là int, số thập phân mặc định sẽ là double**

Kiểu số nguyên sẽ bao gồm: byte, short, int, long và char  
Kiểu số thập phân sẽ bao gồm float và double
Tại sao lại như vậy, cùng xem các ví dụ dưới đây
```java
byte num1 = 1;
char num2 = `a`;
byte num3 = num1 * num2;
```
*num1* và *num2* đều là kiểu số nguyên. Kết quả phép tính của 2 số nguyên sẽ là một số nguyên, và hiển nhiên nó phải là kiểu **int**. Vì thế mà đoạn code trên sẽ có lỗi compile, ta khai báo *num3* kiểu **byte** là sai, phải là **int**

Tương tự, đoạn dưới đây cũng sẽ lỗi compile:
```java
byte num1 = 1;
byte num2 = 100;
byte num3 = num1 * num2;
```

Nhưng nếu như này thì sao:
```java
final byte num1 = 1;
final byte num2 = 100;
byte num3 = num1 * num2;
```
Kết quả không lỗi, do lúc này Java đã chắc chắn *num3* là an toàn nếu để kiểu **byte**
Đoạn dưới đây lại lỗi compile
```java
final byte num1 = 100;
final byte num2 = 100;
byte num3 = num1 * num2;
```
Vì trường hợp này Java đã (nhẩm trong đầu) là *num3* chắc chắn mang giá trị vượt kiểu **byte**, nên sẽ lại bắt nó mang kiểu **int**. Khá là rối rắm.  
Xem tiếp đoạn code sau
```java
long num1 = 2147483648;
```
Bạn nghĩ đoạn trên sẽ ổn vì *2147483648* chẳng là gì so với độ lớn của long. Hãy nhớ lại rằng, khi bạn dùng số nguyên, Java mặc định coi nó là **int**, khai báo kiểu *long* không thay đổi điều đó. Để thông báo cho Java biết là bạn định dùng **long** và giá trị kia là an toàn, bạn phải thêm hậu tố **L** hoặc **l** (thường dùng **L**)
```java
long num1 = 2147483648L;
```
Việc bắt buộc thêm hậu tố vào hơi phiền phức.

Với kiểu dữ liệu thập phân, đoạn code dưới đây cũng lỗi vì bạn đang gán giá trị thập phân nhưng lại khai báo kiểu **float**. Cần thêm hậu tố **f** hoặc **F** (thường dùng **f**) tương tự như với **long**
```java
float num1 = 10.0;
```
Sửa lại như sau
```java
float num1 = 10.0f;
```
hoặc 
```java
float num1 = 10;
```
**float** rộng hơn **int** nên đoạn trên được chấp nhận.

Có thể bạn sẽ nghĩ đoạn dưới đây lỗi
```java
float num1 = 1;
float num2 = 100;
float num3 = num1 * num2;
```
nhưng không có lỗi nào ở đây cả. Đoạn trên chạy hoàn toàn bình thường.

Tương tự như **float** và **long**, thì **double** cũng có hậu tố là **D** hoặc **d** (thường dùng **d**)

>Fact: Người ta sẽ hay dùng *f* và *d* cho **float** và **double**. Nhưng sẽ dùng *L* cho **long** thay vì *l*. Vì *l* sẽ nhìn khá giống *I* (i nhưng in hoa) trong nhiều font chữ. Vậy nên dùng *L* cho dễ phân biệt.

**Trong các phép toán, kiểu dữ liệu cao hơn sẽ được ưu tiên, trừ khi ép kiểu**

Các code sau là hợp lệ:
```java
byte num1 = 1;
int num2 = 2;
int num3 = num1 * num2;
int num4 = 'f';
long num5 = num4;
float num6 = num5;
double num7 = num6; 
```
Nhưng nếu đi ngược lại như dưới đây sẽ lỗi ngay lập tức
```java
float num1 = 1.1f;
int num2 = num1;
```
cần phải ép kiểu
```java
float num1 = 1.1f;
int num2 = (float)num1;
```
Chuyện gì sẽ xảy ra khi ta ép kiểu cho một biến mang giá trị nằm ngoài kiểu dữ liệu đích.
Ví dụ
```java
int num1 = 200;
byte num2 = (byte) num1;
System.out.println(num2);
```
kết quả ra -56, không có lỗi nào được trả ra. Khá giống với trường hợp gán một giá trị vượt ngoài độ dài của kiểu dữ liệu, cần đặc biệt chú ý vấn đề này.  
Ép kiểu từ số thập phân sang số nguyên cũng làm mất đi phần thập phân.
```java
float num1 = 97.3f;
char num2 = (char)num1;
System.out.println(num2);
```
Kết quả ra *a*, phần thập phân bị loại bỏ

**Không thể ép kiểu hoặc sử dụng những kiểu dữ liệu không tương thích nhau**

Ngoại trừ Numeric và Character có thể ép kiểu qua lại, những kiểu dữ liệu khác nhau không thể được sử dụng hoặc ép kiểu.
Không thể viết:
```java
boolean flag = true;
flag = 2;
```
hay
```java
boolean flag = (boolean)2;
String text = (String)2;
```

**Không thể dùng biến nguyên thủy cho Generic types**

Generic types sẽ được giải thích trong các chương tiếp theo. Generic yêu cầu kiểu là một class cụ thể, mà kiểu nguyên thủy không phải là class, không phải object nên không thể sử dụng với Generic là lẽ tự nhiên.
Sẽ không có những kiểu dùng như sau
```java
var list = new ArrayList<int>();
```
Thay vào đó, sẽ có các Wrapper Classes thay thế cho các kiểu nguyên thủy để sử dụng với Generic types.  
Wrapper classes sẽ được giải thích trong các chương tiếp theo.
```java
var list = new ArrayList<Integer>();
```

### Objects

Ngoại trừ kiểu dữ liệu nguyên thủy thì tất cả đều là Objects. Objects sẽ được giải thích trong các chương tiếp theo.