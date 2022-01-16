# Xâu trong C++

1. [Giới thiệu](#introduction)
2. [Các phương thức và phép toán của kiểu string](#method)
a. [Các phép toán và phương thức cơ bản](#basic_operator)
b. [Chèn, xóa, lấy xâu con](#insert_erase)
c. [So sánh](#compare)
d. [Phương thức tìm kiếm và thay thế](#find_replace)
e. [Tách xâu](#stoken)

## 1. Giới thiệu <a name="introducton"></a>

---

- **string** là một kiểu dữ liệu được định nghĩa trong thư viện string của ngôn ngữ C++.

- **string** là một lớp chuẩn mô tả về xâu kí tự, cung cấp khả năng lưu trữ xâu kí tự và thêm vào đó một số thiết kế để xử lí xâu kí tự mà nó đâng lưu trữ.

Để sử dụng nó chúng ta cần khai báo các chỉ thị `#include` liên quan để sử dụng như :`#include<string>`

- Khai báo Xuất, nhập **string**:
  - Như khai báo một mảng với kiểu dữ kiệu xác định, xâu có thể được khai báo bằng các cách:

``` C++
#include<iostream>
#include<string>
using namespace std;
int main() 
{
    string a = ""; // khai báo xâu a rỗng.
    string str = a; // khai báo mội xâu str và gán cho nó giá trị giống xâu đã có trước a
    string Str = "ABC"; // khai báo xâu và gán phần tử cho xâu
}
```

- Sử dụng `cin` kết hợp với toán tử `>>`: lệnh nhập một xâu ký tự đến khi gặp một khoảng trắng hoặc ký tự xuống dòng thì dừng.
- Sử dụng `cout` kết hợp với toán tử `<<`: lệnh in xâu ra màn hình.

``` C++
#include<iostream>
#include<string>
using namespace std;
int main() 
{
    string a; // Khai báo xâu a.
    cin >> a; // Nhập xâu a
    cout << a; // in xâu a ra màn hình
}
```

Kết quả nhận được
>Input: hoala
>Output: hoala

- Để nhập vào một xâu đến khi gặp kí tự kết thúc: sử dụng `getline`

```C++
#include<iostream>
#include<string>
using namespace std;
int main() 
{
    string str;
    char c = '.'; 
    getline(cin, str, c); // Nhập dữ kiệu vào xâu str đến khi gặp dấu . 
}
```

Nhập vào
>Hello IT.

In ra
>Hello IT

## 2. Các phương thức và phép toán của kiểu string <a name="method"></a>
---

#### a. Các phương thức cơ bản và phép toán cơ bản <a name="basic_operator"></a>

- Các toán tử  `+` và `+=` dùng để ghép 2 xâu

```C++
#include <iostream>
#include <string>

using namespace std;
int main () 
{
    string str = "Hello", str1 = "world!";
    string str_sum = str + " " + str1;
    cout << str_sum;
}
```

Kết quả sau khi chạy chương trình:
>Hello world!

- Các phép so sánh theo thứ tự từ điển `==` (bằng nhau), `!=`(khác nhau), `>` (lớn hơn), `<` (nhỏ hơn), `<=`, `>=`.

- Phép gán `=` dùng để gán biến kiểu **string** bằng một xâu (Ex: `str = "ABCD"`) hoặc gán bằng một bến kiểu **string** khác (Ex: `str1 = str2`), mà không cần copy xâu.

- String thực chất là 1 `vector<char>` có bổ sung thêm một số hàm và thuộc tính. Nó có toàn bọ các tính chất của 1 vector. Một vài tính chất:
Giả sử có 1 string v:
    - `v.size()`: Số lượng phần tử
    - `v.empty()`: Trả về 1 nếu xâu rỗng, 0 nếu ngược lại.
    - `v.max_size()`: Trả về số lượng phần tử tối đa đã được cấp phát
    - `v1 == v2`: Trả về 1 nếu hai xâu giống nhau
    - `v1 != v2`: Trả về 1 nếu hai xâu khác nhau
    - `v.front()`: Trả về phần tử đầu tiên của xâu
    - `v.back()`: Trả về phần tử cuối cùng của xâu
    - `v1.swap(v2)`: Hoán đổi 2 xâu với nhau (giống việc hoán đổi giá trị của 2 biến)

- Truy cập vào các phần tử trong xâu theo chỉ số. Chỉ số được tính từ `0` đến `s.ize() - 1`
theo các cách sau:

``` C++ 
#include <string>
#include <iostream>

using namespace std;

int main ()
{
    string str = "ABCD";
    // cách 1
    for (int i = 0; i < str.size(); ++i) cout << str[i]; 
    // cách 2
    for (int i = 0; i< str.size(); ++i) cout << str.at(i);
}
```

#### b. Phương thức chèn, xóa, lấy xâu con <a name="insert_erase"></a>:

- Chèn sử dụng `insert`:

    - `str.insert(int pos, char* s)`; chèn s (mảng ký tự kết thúc \0) vào vị trí pos của str;
    - `str.insert(int pos, string s)`; chèn xâu s (kiểu string) vào vị trí pos của xâu str;
    - `str.insert(int pos, int n, int ch)`; chèn n lần ký tự ch vào vị trí pos của xâu str;

*Sử dụng phương thức **insert** với vị trí chèn không hợp lệ sẽ gây ra lỗi xung đột vùng nhớ*

- Nối thêm một ký tự vào string: (Ký tự này sẽ được thêm vào sau phần tử cuối cùng của **string**) sử dụng phương thức `push_back`

- Nối thêm một xâu ký tự vào string (xâu này được thêm vào cuối **string** ban đầu) sử dụng phương thức `append()`

```C++
string str="Hello";
str.append("world!");
// khi đó str = "Helloworld!"
string s = "I'm";
str.append(s);
// khi đó str = "Helloworld!I'm";
str.push_back('.'); // str = "Helloworld!I'm."
``` 

- Xóa tất cả các phần tử trong xâu sử dụng `clear()`
- Xóa phần tử cuối cùng của xâu sử dụng phương thức `pop_back()`
- Xóa `n` ký tự của xâu `str` kể từ vị trí `pos`. (nếu không quy định giá trị `n` thì tất cả các ký tự từ vị trí `pos` trở đi sẽ bị xóa) sử dụng phương thức `erase(int pos, int n)` *(`pos` ở đây là theo chỉ số)*

```C++
#include <iostream>
#include <string>

using namespace std;
int main()
{
    string s = "ABC", s1 = "def"
    s += s1; //s = "ABCdef"
    s.pop_back();
     // s = "ABCde", xóa ký tự cuối cùng của xâu s
    s.erase(4); // s = "ABCd" xóa các ký tự kể từ vị trí thứ 4 đến cuối s
    s.erase(2, 2); // s = "AB" xóa từ vị trí thứ 2, xóa 2 ký tự

    s.clear() // s = ""; xóa toàn bộ các phần tử của s
} 
```

- Phương thức `substr(int pos, int nchar)` trích ra một xâu con của một xâu con cho trước. TRả vè xâu con gồm `nchar` ký tự của xâu kể tử vị trí `pos` (tính theo chỉ số).

```C++
string str="ABCde";
string s = str.substr(3, 2);
// s = "de"
```

#### c. So sánh <a name="compare"></a>

Ngoài việc sử dụng các toán tử quan hệ(`==`, `!=`, `<`,`>`, `<=`, `>=`), nếu muốn so sánh một phần của một xâu thì sẽ cấn sử dụng phương thức `compare`
    - `compare ( const string& str )`; 
    - `compare ( size_t pos1, size_t n1, const string& str )`;
    - `compare ( size_t pos1, size_t n1, const string& str, size_t pos2, size_t n2 )`;
Hàm trả về `0` khi hai xâu bằng nhau và lớn hơn hặc nhỏ hơn không trong trường hợp khác.
```C++
#include <iostream>
#include <string>
using namespace std;
int main ()
{
    string str1 ("green apple");
    string str2 ("red apple");
    if (str1.compare(str2) != 0) // so sánh str1 và str2
    cout << str1 << " is not " << str2 << "\n";
    if (str1.compare(6,5,"apple") == 0) so sánh 5 kí tự kể từ ký tự có chỉ số là 6 của xâu str với xâu "apple" 
    cout << "still, " << str1 << " is an apple\n";
    if (str2.compare(str2.size()-5,5,"apple") == 0) // so sánh 5 ký tự cuối cùng của xâu str2 và "apple"
    cout << "and " << str2 << " is also an apple\n";
    if (str1.compare(6,5,str2,4,5) == 0)// so sánh 5 kí tự kể từ vị trí thứ 6 của xâu str1 với 5 kí tự kể từ kí tự thứ 4 của xâu str2
    cout << "therefore, both are apples\n";
    return 0;
}
/* Kết quả khi chạy chương trình:
green apple is not an apple
still, green apple is an apple
and red apple is also an apple
therefore, both are apples
*/
```
Với `str1.compare(str2)`:

- Giá trị trả về nhỏ hơn 0:

Điều này có nghĩa tại vị trí phát hiện cặp kí tự không tương xứng giữa str1 và str2 tạm gọi là vị trí `index_not_match`, ta có:
    `str1[index_not_match] < str[index_not_match]`

- Giá trị trả về lớn hơn 0: Ngược lại.

#### d. Các phương thức tìm kiếm và thay thế

- Tìm kiếm với phương thức `find()`: tìm kiếm xem có xâu hay ký tự nào đó có xuất hiện trong xâu `str` hay không.
    - `str.find(char ch, int pos = 0)`; tìm ký tự ch kể từ vị trí pos đến cuối xâu str
    - `str.find(char *s, int pos = 0)`; tìm s (mảng ký tự kết thúc ‘\0’) kể từ vị trí pos đến cuối
    - `str.find(string& s, int pos = 0)`; tìm xâu s kể từ vị trí pos đến cuối xâu.
Nếu không quy định giá trị `pos` thì mặc định là tìm kiếm từ vị trí ban đầu. Hàm trả về vị trí xuất hiện đầu tiên nếu có hoặc trả về `-1` nếu không tìm thấy.
- Thay thế: Phương thức `replace()` thay thế một đoạn con trong xâu `str` cho trước (đoạn con kể từ một vị trí `pos` và đếm tới `nchar` ký tự ký tự về phía cuối xâu) bởi một xâu `s` nào đó, hoặc bởi `n` ký tự `ch` nào đó. Có nhiều cách dùng, thứ tự tham số như sau:
    - `str.replace(int pos, int nchar, string s)`; thay thế bỏi xâu s
    - `str.replace(int pos, int nchar, int n, char ch)`; thay thế bơi n kí tự `ch`
```C++
string str = "ABC", str2 = "degh";
str.replace(0, 2, srt2); // str = "deghC"
str.replace(0, 2, 4, 'a'); // str = "aaaaC"
```
#### e. Tách xâu

- Tách xâu với `stringstream` (khai báo thứ viện `#include<stringstream>`):
```C++
string S = "Hom nay là thu hai";
stringstream ss(S);

while (ss >> token) // đọc lần lượt các phần của xâu, các phần cách nhau bỏi dấu cách hoặc xuống dòng.
{
    cout << token << "\n";
}
```
- Tách xâu sử dụng `strtok(str, sep)`; `str` là xâu cần tách, `sep` là ký tư phân tách(để sử dụng strtok cần dùng mảng kí tự, vì vậy cần chuyển **string** sang dạng mảng kí tự).
Hàm strtok() sẽ trả về vị trí đầu xâu của xâu con đầu tiên được phân tách bằng dấu phân cách từ xâu ban đầu dưới dạng con trỏ xâu trong C. Trong trường hợp không tìm thấy ký tự phân tách , giá trị NULL sẽ được trả về.

Cơ chế của hàm strtok() là điền ký tự kết thúc xâu \0 vào xâu ban đầu mỗi khi tìm thấy ký tự phân tách, do đó cần lưu ý là hàm strtok() sẽ làm biến đổi xâu ban đầu.
Lại nữa, hàm strtok() chỉ có thể tách một xâu con bằng dấu phân tách từ xâu ban đầu trong mỗi lần thực thi mà thôi.
```C++
#include <iostream>
#include <string>
#include <bits/stdc++.h>
using namespace std;
int main ()
{
    string S="hom nay khong hoc";
    char s[100];
    strcpy(s, S.c_str());
    char* p;
    p = strtok(s, " ");
    cout << p << " ";
    while (p != NULL) 
    {
      p = strtok(NULL, " ");
      cout << p << " ";
    }
}

```

- Tách xâu sử dụng find()

```C++
string S="hom nay khong phai thu hai";
string:: iterator t, t2;
for (t = S.begin(); t < S.end();) 
{
    t2 = find (t, S.end(), ' ');
    if (t != t2) cout << string(t, t2);
    t = t2 + 1;
}
```
Đoạn chương tr.nh sử dụng các kỹ thuật sau
- Phương thức `find(vị_trí_đầu, vị_trí_cuối, ký_tự_tìm)` dùng để tìm vị trí đầu tiên của ký_tự_tìm bắt đầu từ vị_trí_đầu. Hàm này trả về vị trí của ký tự tìm được (nếu tìm thấy) hoặc vị_trí_cuối (nếu không tìm thấy)
- `string` có thể khởi tạo từ một đoạn ký tự con của một xâu ký tự khác với cú pháp `string(vị_trí_đầu, vị_trí_cuối)`. Đoạn chương trình thực hiện tách các xâu ký tự kể cả trong trường hợp có nhiều ký tự space nằm liên tiếp nhau