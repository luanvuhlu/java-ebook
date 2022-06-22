# Chương 1. Java là gì

Java là một ngôn ngữ lập trình được phát triển bởi James Gosling tại Sun Microsystems. Phiên bản 1.0 được ra đời năm 1995.
Java ban đầu được ra đời nhằm dễ dàng thay thế C/C++ để chạy trên các thiết bị mạng và hệ thống nhúng. Tuy nhiên, team Java nhận ra nó quá to lớn so với mục đích ban đầu. Thêm việc bùng nổ của internet và web những năm đó, Java đã trở thành một trong những ngôn ngữ lập trình được dùng rộng rãi nhất, xuất hiện không chỉ trong những ứng dựng thiết yếu trên internet mà còn trong hàng tỷ thiết bị gia dụng, thiết bị thông minh.  

Mục tiêu thiết kế của Java bao gồm:

*   Đơn giản, hướng đối tượng và quen thuộc
*   Mạnh mẽ và bảo mật
*   Kiến trúc trung lập và Portable
*   Hiệu năng cao
*   Interpreted, Threaded, và Dynamic

> Fact: Kể từ lúc xuất hiện năm 1995, Java chưa bao giờ rời khỏi vị trí top 3 những ngôn ngữ lập trình thông dụng nhất.

+++

Java được lấy ý tưởng rất nhiều từ C/C++, đặc biệt là cú pháp. Nhưng đương nhiên, Java đặc biệt loại bỏ một số thứ từ C/C++ mà họ thấy không hợp lý, có thể kể đến:

#### Không Structures, Unions, Functions
Để đơn giản hóa Java và hướng nó đến là ngôn ngữ lập trình thuần hướng đối tượng, những cấu trúc và phong cách code không phù hợp bị loại bỏ.

#### Không Enums
Với cùng lý do trên, họ đã từng nghĩ rằng Enums là một thứ bất hợp lý. Nhưng đến cuối cùng, Enums quá tiện lợi nên đã được thêm vào trong phiên bản 1.5. Và giờ đây, sử dụng Enums cũng trở thành một coding convention tiêu chuẩn.

#### Không đa kế thừa
Đa kế thừa trong C++ quả thực là quá rối rắm và phức tạp. Nếu đặt nó trong tay sai người sẽ trở thành ác mộng. Java muốn dùng Interfaces để thay thế. Tuy nhiên Interfaces sẽ khó cho việc sử dụng lại code, điều mà đa kế thừa dễ dàng đạt được. Vì lẽ đó mà Java ngày càng cải tiến Interfaces để khắc phục.

#### Không Pointers
Gần như không có ai dám nghi ngờ Pointer trong ngôn ngữ lập trình thực sự là quá khó tiếp cận và dễ xảy ra lỗi. Loại bỏ pointer rõ ràng là việc làm đúng đắn. Sự thật là một vài ngôn ngữ lập trình hiện đại vẫn dùng Pointer nhưng đã mang hàm nghĩa khác so với Pointer trong C/C++.

+++

Thuở sơ khai, Java bị phàn nàn là chạy chậm hơn C/C++ quá nhiều. Qua nhiều cải tiến cho đến tận ngày nay, Java vẫn chậm hơn C/C++. Nhưng hóa ra, phần cứng ngày càng phát triển, một chút nhanh chậm của một vài dòng code không phải lúc nào cũng là vấn đề quá to tát. Ngược lại, một ngôn ngữ lập trình dễ tiếp cận, đáng tin cậy lại quan trọng hơn.  
Bù vào khuyết điểm tốc độ, Java lại có ưu điểm so với C/C++ hay ngay cả các ngôn ngữ khác:

#### Không phụ thuộc vào nền tảng
"Write once, run everywhere" là slogan marketing vô cùng thành công của Java. Những ngôn ngữ C/C++ bị phụ thuộc nền tảng. Khi bạn thay đổi từ Linux sang Window hay MacOS, bạn phải biên dịch lại toàn bộ code. Thậm chí việc biên dịch chưa chắc đã thành công. Ngược lại, Java chỉ cần được biên dịch ra bytecode một lần và chạy được ở bất kỳ đâu có Java Virtual Machines.
Java không phải là ngôn ngữ đầu tiên hay cuối cùng có thể "write once, run anywhere", rất nhiều ngôn ngữ có thể làm tương tự như PHP, Python với trình thông dịch, hay Javascript, Ruby, Smalltalk dùng Virtual Machines giống Java có thể làm được. Nhưng nếu nhìn vào những nơi Java có thể xuất hiện: máy tính, điện thoại, tivi, tủ lạnh, đầu đọc thẻ,... thì rõ ràng không có ngôn ngữ nào dám phủ nhập cái slogan đó cả.

#### Đơn giản, dễ học nhưng mạnh mẽ
Nếu so sánh với C/C++ thì Java đơn giản hơn rõ ràng. Ngôn ngữ đơn giản, dễ lập trình, dễ sửa lỗi, có nhiều công cụ hỗ trợ lập trình vô cùng mạnh mẽ. Khá dễ hiểu vì sao Java lại được lựa chọn cho những chương trình lớn.
Đơn giản là thế, nhưng Java cũng đi kèm sẵn rất nhiều thư viện giúp bạn dễ dàng xây dựng các chương trình lớn mà không cần phải thêm quá nhiều thư viện ngoài. Có thể kể đến những thư viện sẵn có trong Java APIs:

*   IO/NIO
*   Networking
*   Reflection
*   Concurrency
*   Generics
*   Scripting/Compiler
*   Collections
*   XML
*   Security
*   Internationalization and localization
*   Database
*   Java Naming and Directory Interface (JNDI) for lookup and discovery
*   RMI and CORBA for distributed application development
*   JMX for managing and monitoring applications
*   User interface libraries, which include:
*   GUI widget toolkit(AWT, Swing, JavaFX)
*   APIs for audio/video capture, processing, and playback

và nhiều thư viện khác nữa.

+++

Sun Microsystems được Oracle mua lại năm 2009, qua đó Oracle tiếp quản Java. Qua 27 năm phát triển, Java thay đổi rất nhiều, đặc biệt 5 năm gần đây, bổ sung rất nhiều cú pháp và các tính năng mới. Đồng thời Oracle cũng vun đắp nền tảng Java, cải thiện hiệu suất, mở rộng sang các khía cạnh khác như native, cloud, serverless,...Nhưng ngược lại, cũng mang đậm tính thương mại.

### Kết luận
Chúng ta đã được biết qua được lịch sử hình thành và phát triển của Java. Java là một ngôn ngữ lập trình mạnh mẽ và vô cùng thông dụng ngày nay. 