Meow
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

> VM là viết tắt của Virtual machine tức máy ảo, là 1 trình giả lập hệ thống máy tính.

*Đáp án là: virtual machine*

---
## Task 2 <a name="t2"></a>

> Tool giúp người dùng tương tác với máy tính qua các câu lệnh (command line) còn được biết là console hay shell: đó là terminal

*Đáp án là: terminal*

---
## Task 3 <a name="t3"></a>

> Service được sử dụng để tạo VPN connection từ máy tính tới HTB lab là openvpn

*Đáp án là: openvpn* 

---
## Task 4 <a name="t4"></a>

> Viết tắt của tunnel interface, là đầu ra của VPN connection là: tun (tun0, tun1,...)

*Đáp án là: tun*

---
## Task 5 <a name="t5"></a>

> Tool để test connection sử dụng ICMP là: ping

*Đáp án là: ping*

---
## Task 6 <a name="t6"></a>

> Tool thông dụng nhất để scan các port đang mở trên 1 hệ thống là: nmap

*Đáp án là: nmap*

---
## Task 7 <a name="t7"></a>

Câu này hỏi về service đang mở ở port 23, chúng ta tiến hành dùng nmap scan target với câu lệnh sau:

```
nmap -vv -T4 -Pn -sV <machine-ip>
```

![](https://i.imgur.com/T31XrgK.png)

Kết quả cho thấy service đang chạy ở port 23 là telnet

*Đáp án là: telnet*

---
## Task 8 <a name="t8"></a>

Thử kết nổi remote tới target machine bằng telnet với câu lệnh sau:

```
telnet <machine-ip>
```

Mình thử sử dụng tài khoản root với password để trống thì thành công kết nối tới target:

![](https://i.imgur.com/W38X6rG.png)

*Đáp án là: root*

---
## Task 9 <a name="t9"></a>

Chúng ta sẽ tìm xung quanh target machine để xem root flag giấu ở đâu, thường thì nó nằm ở /root:

![](https://i.imgur.com/eWi3A9G.png)

Tìm được flag, hoàn thành room

*Đáp án là: b40abdfe23665f766f9c61ecba8a4c19*
