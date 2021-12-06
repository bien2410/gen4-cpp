## Mảng 1 chiều

#### 1. Khái niệm và cách sử dụng mảng 1 chiều
#### 2. Khai báo, duyệt các phần tử mảng
#### 3. Kỹ thuật mảng đánh dấu
#### 4. Kỹ thuật sắp xếp mảng
#### 5. Các bài toán tìm kiếm trong mảng đã sắp xếp trình tự
### Buổi 4
**1.**

- Mảng là một loại cấu trúc dữ liệu trong ngôn ngữ lập trình C/C++, nó lưu trữ một tập hợp tuần tự các phần tử cùng kiểu với độ dài cố định. Mảng thường được sử dụng để lưu trữ tập hợp dữ liệu, nhưng nó cũng hữu dụng khi dùng để lưu trữ một tập hợp biến có cùng kiểu.

- Thay vì khai báo biến một cách rời rạc, như biến bien1, bien1,… và bien99, bạn có thể khai báo một mảng các giá trị như bien[0], bien[1] và … bien[99] để biểu diễn các giá trị riêng biệt. Một phần tử cụ thể của mảng có thể được truy cập qua index (chỉ số).

- Tất cả mảng đều bao gồm các vị trí nhớ liền kề nhau. Địa chỉ thấp nhất tương ứng với phần tử đầu tiên và địa chỉ cao nhất tương ứng với thành phần cuối cùng của mảng.

**2.**

**a. Khai báo mảng**

Khai báo đảm bảo khởi tạo được số phần tử cố định của mảng
``` 
    [Kiểu dữ liệu] [Tên mảng][số phần tử mảng] = {khởi tạo các giá trị của các phần tử cho mảng};
```

Quy định về đặt tên mảng tương tự như quy định về đặt tên 1 biến. 

Ví dụ một vài cách khai báo mảng:
```
    int a[1000]; // Khai báo mảng a gồm 1000 phần tử, tất cả các phần tử đều có kiểu dữ liệu int.

    char c[200]; // Khai báo mảng c gồm 200 phần tử có kiểu dữ liệu kí tự.

    int a[] = {1, 3, 4}; // khai báo mảng 1 chiều a gồm 3 phần tử được xác định giá trị thuộc kiểu số nguyên int

    int a[100] = {0}; // khai báo mảng 100 phần tử số nguyên, đồng thời gán tất cả phần tử bằng 0.

    char c[3] = {'a', 'b', 'c'}; // khai báo mảng kí tự 3 phần tử đồng thời gán giá trị cho 3 phần tử.
```

Có thể xác định só lượng phần tử của mảng bằng giá trị của 1 biến xác định.
``` 
    int n = 10;
    int a[n]; // tương đương với việc khai báo  int a[10];
```
**Note:**
Khi khai báo `int a[1000];` các giá trị của các phần tử trong mảng `a` không được tự động gán bằng `0` mà mang `1` giá trị rác tùy vào vị trí trong vùng nhớ của các phần tử.

**b. Nhập, in mảng**

- Sử dụng `vòng lặp` để truy cập vào từng phần tử trong mảng theo chỉ số.
- Chỉ số cho biết thứ tự phần tử trong mảng, bắt đầu từ 0 với phần tử đầu tiên. Ví dụ với mảng gồm n phần tử, chỉ số các phần tử trong mảng sẽ bắt đầu từ 0 đến n - 1 là chỉ số của phần tử cuối cùng. 

- In mảng: 
```php
    int a[5] = {1, 2, 3, 4, 5};
    for (int i = 0; i < 5; ++i) cout << a[i] << " ";
```
- Nhập mảng từ bàn phím:
```php
    int a[5];
    for (int i = 0; i < 5; ++i) cin >> a[i];
```

**3.**


 

