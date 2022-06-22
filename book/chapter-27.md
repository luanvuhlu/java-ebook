# Arrays

**Arrays** là một object đặc biệt dùng để chứa tập hợp các giá trị khác với số lượng tối đa là không đổi.  
Ví dụ bạn có một array với số lượng tối đa là 10, thì bạn không thể thêm quá 10 phần tử vào array này.  
Khai báo array:
```java
var arr1 = new int[10];
var arr2 = {1, 2, 3};
```

### Một số đặc điểm của **arrays**

**Bạn không thể thay đổi kích thước**

Kích thước của **arrays** là cố định, bạn chỉ có thể khởi tạo một array mới nếu muốn thay đổi kích thước của nó
```java
var arr = new int[]{}; // tương đương array có size = 0
arr[0] = 1; // Lỗi ArrayIndexOutOfBoundsException
var arr2 = new int[1]; // tương đương array có size = 1
arr2[1] = 1; // Lỗi ArrayIndexOutOfBoundsException
var arr3 = new int[0]; // tương đương array có size = 0
var arr4 = new int[100]; // tương đương array có size = 100
arr4[1] = 1; // Hợp lệ
```

**Dấu ngoặc vuông [] khi khai báo**

Dấu ngoặc vuông *[]* có thể ở kiểu dữ liệu, tên biến hoặc cả hai, nhưng không thể dùng kèm với từ khóa **var**  
Các cách khai báo sau là hợp lệ
```java
private String[] arr;
private String arr2[];
private String[] arr3[];
```
Khai báo như dưới đây là sai
```java
var[] arr = new int[10];
var arr1[] = new int[10];
```
**Khi gán giá trị**

Bạn phải xác định kích thước của **arrays**, theo cách rõ ràng hoặc ngầm hiểu
```java
var arr1 = new int[10];
var arr2 = new int[]{1, 2, 3};
String arr3[] = { "Hello", "World" };
String[] arr4 = {};
var arr5 = new int[2][1];
var arr6 = new int[2][];
int[] arr7[] = new int[2][1];
int arr8[][] = new int[2][1];
int[][] arr9 = new int[2][1];
int[][][][] arr10 = {{}};
```
Bạn không thể xác định kích thước của **arrays** ở phần khai báo. Đoạn dưới đây là sai:
```java
String[2] arr4 = { "Hello", "World" };
```
Bạn cũng không thể vừa xác định kích thước của **arrays**, vừa gán giá trị cho nó. Đoạn dưới đây là sai:
```java
String[] arr4 = new String[2]{ "Hello", "World" };
```
**Với mảng đa chiều**

Chỉ chiều đầu tiên cần xác định kích thước, những chiều khác có thể không có
```java
int[][] arr1 = new int[2][1];
int[][] arr2 = new int[2][];
int[][][] arr3 = new int[2][][];
int[][][] arr4 = {}; // kích thước bằng new int[0][][]
int[][][][] arr5 = {{}}; // kích thước bằng new int[1][0][][]
```
Tuy nhiên, xác định kích thước nhưng ngắt quãng giữa các chiều cũng là không hợp lệ. Các ví dụ dưới đây là sai
```java
int[][][] arr1 = new int[][][];
int[][][] arr2 = new int[][1][];
int[][][] arr3 = new int[][][1];
int[][][] arr4 = new int[1][][1];
```
**Kiểu dữ liệu**

Kiểu dữ liệu của **arrays** và các phần tử tuân theo nguyên tắc của kiểu dữ liệu nguyên thủy và **objects**, bạn không được phép thêm phần tử có kiểu dữ liệu không tương thích với **arrays**.  
Các ví dụ dưới đây là sai
```java
int[] arr = new int[]{ "Hello" }; // int và String không tương thích
int[] arr2 = { 1f }; // int và float không tương thích
int[] arr3 = new int[2];
arr3[0] = "Hello"; // int và String không tương thích
var arr4 = new Integer[] { BigDecimal.TEN }; // Integer và BigDecimal không tương thích 
```
Các ví dụ dưới đây là hợp lệ
```java
var arr = new BigDecimal[] { BigDecimal.TEN };
var arr2 = new Number[] { BigDecimal.TEN }; // Number là class cha của BigDecimal
var arr3 = new Object[] { "Hello" }; // Object là class cha của mọi class
var arr4 = new char[] { 1, 2 }; // kiểu char chấp nhận số nguyên
```
