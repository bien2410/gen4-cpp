##Kiến thức buổi 1 
```php
> Cấu trúc cơ bản của chương trình C++  
> Lệnh, khối lệnh, từ khóa, comment.
> Lệnh liên quan đến xuất dữ liệu
> Biến và các kiểu dữ liệu trong C++
> Các toán tử và phép toán cơ bản 
```

####1. Chương trình C++ ban đầu
```php
#include<iostream> // thư viện tích hợp

using namespace std; // không gian tích hợp

int main() {
    cout << "Hom nay la thu 7";
    return 0;
}
```

+ Hàm main: (bắt buộc phải có)

	+ Kiểu trả về của hàm main (int).
	+ Tên của hàm main (cũng là main luôn).
	+ Thân của hàm main (cặp dấu ngoặc nhọn { và }).
	+ Giá trị trả về của hàm main (return 0; //hoặc giá trị bao nhiêu cũng đc).


+ Những dòng lệnh bên trong thân hàm main. (Có thể có hoặc không)

+ Những dòng comment. (Có thể có hoặc không)

+ Tích hợp thư viện và không gian tên. (Phụ thuộc vào các lệnh mà bạn sử dụng).


####2. Lệnh, khối lệnh, từ khóa, comment

a. Lệnh
Lệnh là một chỉ thị riêng biệt của một chương trình.
Với những câu lệnh khác nhau nó sẽ chỉ dẫn máy tính thực hiện những công việc khác nhau.
Chú ý: Dòng lệnh kết thúc bằng dấu ;
Tại một thời điểm, chương trình chỉ có thể thực hiện 1 dòng lệnh. Các dòng lệnh được thực hiện tuần tự từ trên xuống dưới.

b. Khối lệnh
- Khối lệnh là tập hợp các câu lệnh được đặt trong dấu ngoặc nhọn {và};

- Một khối lệnh có thể chứa nhiều dòng lệnh, có thể chứa một dòng lệnh hoặc không chứa dòng lệnh nào. Một khối lệnh còn có thể chứa một hoặc nhiều khối lệnh khác.

c. Từ khóa

từ do người tạo ra ngôn ngữ đó định sẵn. Mỗi từ khóa đã được định nghĩa một ý nghĩa riêng. Việc chúng ta kết hợp từ khóa với các cú pháp đi kèm, chúng ta sẽ có được câu lệnh.

![từ khóa](https://raw.githubusercontent.com/nguyenchiemminhvu/CPP-Tutorial/master/1-cpp-co-ban/1-2-lenh-khoi-lenh-tu-khoa/keyword.png)

d. Comment
- Đoạn được comment sẽ không được chạy trong quá trình chươn trình chạy
- Comment 1 dòng
```php
    // cout << "abcde";
```
- Comment nhiều dòng
```php
    /*
    cin >> a
    */
```

####3.Lệnh liên quan đến nhập xuất dữ liệu
- In ra màn hình sử dụng câu lệnh `cout <<` 
Cái được in ra màn hình có thể là : một số, chuỗi kĩ tự ...
- Để in nhiều đối tượng cùng một lúc ngoài việc sử dụng Chuỗi các lệnh `cout <<`  nhiều lần chúng ta có thể dùng `<<` để nối các đoạn cần in ra.
- Trong ngôn ngữ lập trình C++, có một số kí tự trên bàn phím chúng ta không thể đưa trực tiếp vào cặp dấu ngoặc kép để in ra màn hình trong lệnh `cout` được. Chúng ta cần định dạng chúng lại một chút. Sau đây là bảng một số kí tự đặc biệt và cách để in chúng ra màn hình:
![cout](https://user-images.githubusercontent.com/85023342/139535333-c2cb34ea-3f56-402b-b9f9-7e8f580da137.png)

- Nhập dữ liệu `cin` Nhập dữ liệu cho biến đến khi gặp dấu cách.
cú pháp `cin >> <tên biến>;`
có thể nhập dạng số nguyên , kí tự tùy vào kiểu dữ liệu của biến.


####4. Biến và các kiểu dữ liệu
- Biến:  Biến là một ô nhớ đơn lẻ hoặc một vùng nhớ được hệ điều hành cấp phát cho chương trình C++ nhằm để lưu trữ giá trị vào bên trong vùng nhớ đó
 khai báo 1 biến : 
```php
    <Kiểu dữ liệu> <Tên biến> = [Giá trị khởi tạo của biến];
```
* Lưu ý về tên biến:
    Tên biến có thể sử dụng các ứng dụng sau:
    - Dấu gạch dưới _
    - Chữ cái in thường a-z
    - Chữ cái in hoa A-Z
    - Chữ số 0-9
    Không được trùng với các từ khóa, tên biến có phân biệt chữ hoa chữ thường

- Hằng: Giúp đảm bảo giá trị của một biến không bị thay đổi. Một hằng phải được khởi tạo giá trị ngay khi khai báo
Khai báo hằng:
```php
    const <kiểu dữ liệu> <tên biến> = <giá trị>;
    <kiểu dữ liệu> const <tên biến> = <giá trị>;
    #define <tên hằng> <giá trị>
```
Chúng ta có thể dựng một trong ba cách trên


Phần khởi tạo giá trị biến có thể có hoặc không.
Chúng ta có thể khai báo cùng 1 lúc nhiều biến nếu chúng có cùng kiểu dữ liệu, Các biến cách nhau bỏi dấy `,`.
-Kiểu dữ liệu: là thành phần phải có khi khai báo biến giúp xác minh được giới hạn giá trị  biến có thể lưu trữ
![image](https://user-images.githubusercontent.com/85023342/139536247-c523ba4a-fcfa-4fac-80e0-17005ad423d9.png)


####5. Các phép toán
- Phép toán : +, -, *, / , %
- Toán tử gán: `<bien> =  <giá trị>`
- Toán tử so sánh: >, <, <=, >=, ==, != 
- Toán tử tăng giảm : ++i, --i, i++, i--, 
i-=a` `  <-> i = i-a 
i+=a
i*=b