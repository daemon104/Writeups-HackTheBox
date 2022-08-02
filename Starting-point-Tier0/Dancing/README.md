Dancing
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

---
## Task 1 <a name="t1"></a>

> SMB là viết tắt của Server Message Block, là 1 giao thức trên Windows và DOS, có chức năng quản lí file giữa client với server

*Đáp án là: Server Message Block*

---
## Task 2 <a name="t2"></a>

> Port thông dụng của SMB service là 445

*Đáp án là: 445*

---
## Task 3 <a name="t3"></a>

Câu này yêu cầu dùng nmap để scan target, mình sẽ sử dụng câu lệnh sau:

```
nmap -vv -T4 -sV -Pn <machine-ip>
```

![](https://i.imgur.com/H5z9718.png)

Kết quả thu được thì service chạy ở port 445 có tên là microsoft-ds

*Đáp án là: microsoft-ds* 

---
## Task 4 <a name="t4"></a>

> Flag dùng để list tất cả shares đang có trên server của SMB tool là '-L' (smbclient):

![](https://i.imgur.com/bOTnuAz.png)

*Đáp án là: -L*

---
## Task 5 <a name="t5"></a>

Workshares là custom share của admin. Mình thử truy cập nó với blank password như trong câu hỏi thì thành công kết nối được tới server:

```
smbclient \\\\<target-ip>\\<share>
```

![](https://i.imgur.com/hP0f6gX.png)


*Đáp án là: Workshares*

---
## Task 6 <a name="t6"></a>

Đầu tiên, mình dùng câu lệnh ls để list file trong directory hiện tại. 1 số câu lệnh tương tác cơ bản với smb cũng tương tự khi dùng terminal. Sau khi dùng ls, mình thấy 1 directory tên Amy.J, cd tới nó và tiếp tục ls:

![](https://i.imgur.com/8GcGA6E.png)

Tại đây, mình thấy 1 file worknotes.txt, để đọc được nó thì các bạn phải get về vì không thể dùng cat trên server smb. Mình dùng lệnh get:

```
get <filename>
```

![](https://i.imgur.com/dEY6rou.png)

*Đáp án là: get*

---
## Task 7 <a name="t7"></a>

Cat file worknotes.txt thì thấy nó không phải flag cần tìm nên mình mò lại trên smb và tìm thấy file flag:

![](https://i.imgur.com/MMj8BSU.png)

Get về và cat:

![](https://i.imgur.com/ZzHbOFM.png)

![](https://i.imgur.com/DExFzoQ.png)

*Đáp án là: 5f61c10dffbc77a704d76016a22f1664*

