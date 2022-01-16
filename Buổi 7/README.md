# Hàm con - chương trình con
---
1. [Định nghĩa hàm](#1)
2. [Cách định nghĩa 1 hàm mới](#2)
    - [Kiểu dữ liệu trả về](#2.1)
    - [Tên hàm](#2.2)
    - [Các tham số của hàm](#2.3)
    - [Nội dung của hàm](#2.4)
3. [Sử dụng hàm đã được định nghĩa](#3)

---

#### 1. Định nghĩa hàm <a name="1"></a>

- Hàm là một nhóm lệnh, yêu cầu chương trình phải hoàn thành một công việc nào đó.
- Hàm có thể trả về một giá trị nào đó hoặc trả lại kiểu void()
- `int main` là một hàm tiêu biểu, trả lại kiểu `int` là kết quả chạy của chương trình.
- Người dùng có thể dùng các hàm đã được xâu dựng hoặc tự định nghĩa hàm trong chương tình của mình.

#### 2. Cách định nghĩa một hàm mới <a name="2"></a>
- Cú pháp để định nghĩa một hàm mới:
```C++ 
[kiểu_dữ_liệu_trả_vê] [Tên_hàm] (tham_số_truyền_vào) 
{
    Nội_dung_của_hàm;
}
```
##### a. Kiểu dữ liệu trả về <a name="2.1"></a>

- Hàm có trả về kết quả: Kết quả đó có thể thuộc kiểu dữ liệu `int`, `double`, .. hoặc các kiểu dữ liệu tự định nghĩa.
- Hàm có thể chỉ thực hiện phép tính mà không trả về kiểu gì cả - Khi đó kiểu dữ liệu trả về được đặt là `void`
- VD : Đối với một hàm tính tích 2 số -> kiểu dữ liệu trả về là kiểu số nguyên.

##### b. Tên của hàm <a name="2.2"></a>

- Quy tắc đặt tên của hàm cũng giống như quy tắc đặt tên biến.

##### c. Các tham số của hàm <a name="2.3"></a>

- Các hàm có thể truyền vào một hoặc nhiều tham số để hoạt động, cũng có thể không truyền vào tham số nào (như hàm `int main()`).
- Các tham số truyền vào được định nghĩa như khai báo biến 
`kieu_du_lieu` `ten_bien`, nếu nhiều tham số thì các tham số cách nhau bởi dấu `,`.

Tham số của hàm có 3 dạng:

- **Tham số truyền giá trị (tham trị**: Đây là kiểu tham số mặc định của hàm. Khi ta gọi hàm, chương trình sẽ tạo ra các biến mới, copy giá trị được truyền vào biến, và tất cả các thay đổi sẽ chỉ diễn ra trên các biến mới này. 
```C++
#include <iostream>

using namespace std;

void daoSo(int a, int b)
{
    int temp = a;
    a = b;
    b = temp;
}

int main()
{
    int a = 10, b = 20;
    daoSo(a, b);
    cout << "a = " << a << "\n";
    cout << "b = " << b;
    return 0;
}
/* Khi chạy kết quả thu được 
a = 10
b = 20

```
Giá trị của a, b ở hàm `main` đều được giữ nguyên
Trong trường hợp này biến a, b trong khai báo hàm `daoSo` không phải là biến `a`, `b` trong hàm `main` mà chỉ là một biến phụ có giá trị được sao chéo từ hai biến `a`, `b` của hàm main. Ở đây chúng ta có thể đổi tên 2 tham số trong phần định nghĩa hàm `daoSo` thành tên bất kì khác mà không ảnh hướng đến công việc của hàm.

- **Tham số truyền biến (tham chiếu):**

    - Khi đố việc khai báo tham số trong hàm được khai báo theo cú pháp: `kieu_dl &ten_bien;`
    - Kiểu tham số này thực hiện mọi thay đổi trực tiếp lên biến truyền vào mà không thông qua biến copy nào.
    - tên tham số trong khỏi tạo hàm có thể là tên bất kì không liên quan đến tên biến truyền dữ liệu vào.
```C++
#include <iostream>

using namespace std;

void daoSo(int &a, int &b)
{
    int temp = a;
    a = b;
    b = temp;
}

int main()
{
    int a = 10, b = 20;
    daoSo(a, b);
    cout << "a = " << a << "\n";
    cout << "b = " << b;
    return 0;
}
/* Kết quả thu được
a = 20
b = 10
```


- **Tham số truyền con trỏ:** TRuyền giá trị địa chỉ ô nhớ của biến vào hàm
Cú pháp: `kiểu_dữ_liệu *tên biến`

##### d. Nội dung của hàm<a name="2.4"></a>
- Nội dung của hàm là những việc ta cần hàm thực hiện, được biểu diễn trong khối lệnh ngoặc nhọn.

```C++
int sum(int a, int b) 
{
    return a+b;
}
```
- Trong hàm `sum` là hàm thực hiện tính tổng giá trị được truyền vào. Giá trị trả về của hàm được thực hiện thông qua lệnh `return gia_tri;` Khi gặp lệnh `return` này hàm trả về giá trị và kết thúc việc thực hiện dù phía sau còn lệnh.
- Một hàm được định nghĩa trả về một kiểu giá trị khác void mà kết thúc không có `return` sẽ khiến chương trình bị lỗi `undefined behavior`. Các bộ dịch không nhất thiết cần phải thông báo lỗi này (nhưng thường sẽ có cảnh báo), và chương trình vẫn có thể được dịch thành công kể cả khi có lỗi này. Khi đó giá trị trả về có thể là bất cứ giá trị nào. Để tránh sai sót, hãy luôn kết thúc các hàm một cách hợp lệ.

Từ khóa `return` cũng có thể sử dụng trong hàm kiểu    `void` để kết thúc hàm đó. Trong trường hợp này, ta không cần có phần giá trị trả về.
```C++
void testing()
{
    cout << "Dong nay se duoc in ra!";
    return;
    cout << "Dong nay se khong duoc in ra, vi chuong trinh con ket thuc roi!";
}
// KKQ: Dong nay se duoc in ra!
```

#### 3. Sử dụng hàm đã được định nghĩa <a name="3"></a>
Sau khi đã định nghĩa hàm, ta có thể sử dụng hàm bằng cách gọi tên của hàm cùng với giá trị của các tham số của nó (nếu có).
```C++
#include <iostream>

using namespace std;

int tinhTong(int a, int b)
{
    return a + b;
}

int main()
{
    cout << tinhTong(1, 2);
    return 0;
}
```
Ở đây chúng ta gọi hàm `tinhTong` và đưa vào 2 giá trị tương ứng với 2 tham số của hàm. Giá trị này có thể thay bằng 2 biến, tham số sẽ copy giá trị được truyền vào và thục hiện công việc.

Một ví dụ về `tham số truyền biến`:
```C++
#include <iostream>

using namespace std;

void tinhTong(int &a, int &b)
{
    a += b;
}

int main()
{
    int a = 1, b = 2;
    tinhTong(a, b);
    cout << "a = " << a;
    return 0;
}
// a = 3
```
Hàm truyền biến: đối tượng được truyền trong lệnh gọi hàm phải là một biến, Đây là một hàm trả về `void` nên có thể gọi hàm như một lệnh thông thường, không thể thực hiện gán hay in giá trị của hàm vì hàm không trả về giá trị nào cả. 