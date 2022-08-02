Fawn
===

Link: https://app.hackthebox.com/starting-point

---
## Mục lục <a name="menu"></a>

* [Mục lục](#menu)
* [Task 1](#t1)
* [Task 2](#t2)
* [Task 3](#t3)
* [Task 4](#t4)
* [Task 5](#t5)
* [Task 6](#t6)
* [Task 7](#t7)
* [Task 8](#t8)
* [Task 9](#t9)

---
## Task 1 <a name="t1"></a>

> FTP là viết tắt cảu File Transfer Protocol, là 1 giao thức truyền file phổ biến

*Đáp án là: file transfer protocol*

---
## Task 2 <a name="t2"></a>

> Service ftp mặc định chạy ở port 21

*Đáp án là: 21*

---
## Task 3 <a name="t3"></a>

> Từ viết tắt của service ftp level security là sftp

*Đáp án là: sftp* 

---
## Task 4 <a name="t4"></a>

> Câu lệnh gửi echo request ICMP tới machine target để test connection là ping

*Đáp án là: ping*

---
## Task 5 <a name="t5"></a>

Câu này cần chúng ta dùng nmap scan target, mình sử dụng câu lệnh sau:

```
nmap -vv -T4 -Pn -sV <machine-target>
```

![](https://i.imgur.com/nUzs2XY.png)

Kết quả thu được version của ftp service là: vsftpd 3.0.3

*Đáp án là: vsftpd 3.0.3*

---
## Task 6 <a name="t6"></a>

Để có thông tin về OS của máy target, ta sử dụng nmap với flag -O:

```
nmap -vv -T4 -Pn -sV -O <machine-ip>
```

![](https://i.imgur.com/RcscdTy.png)

Dựa vào kết quả nmap, OS đang chạy trên máy target là unix 

*Đáp án là: unix*

---
## Task 7 <a name="t7"></a>

> Để show help table của ftp, chúng ta dùng câu lệnh ftp -h

*Đáp án là: ftp -h*

---
## Task 8 <a name="t8"></a>

Để trả lời câu hỏi này, chúng ta tiến hành ftp đến máy target bằng câu lệnh sau:

```
ftp <machine-ip>
```

Khi được hỏi username và password, mình sẽ dùng 1 account phổ biến đó là anonymous:anonymous

![](https://i.imgur.com/x1uPpm3.png)

Thành công kết nối tới target!

*Đáp án là: anonymous*

---
## Task 9 <a name="t9"></a>

Tiếp theo, mình dùng lệnh dir để xem các directory và file tại thư mục hiện tại trên ftp server:

![](https://i.imgur.com/jsYSW3b.png)

Thầy 1 file flag.txt, mình get về và mở ra đọc thì lấy được root flag:

![](https://i.imgur.com/ZSJ4cnj.png)

![](https://i.imgur.com/NF4d6M7.png)

*Đáp án là: 035db21c881520061c53e0536e44f815*
