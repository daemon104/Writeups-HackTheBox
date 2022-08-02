Redeemer
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
* [Task 10](#t10)
* [Task 11](#t11)

---
## Task 1 <a name="t1"></a>

Câu này yêu cầu thông tin về open port, mình sẽ dùng nmap scan target với câu lệnh sau:

```
nmap -vv -T4 -Pn -sV -p1-20000 <target-ip> 
```

Mình scan 1000 port thông dụng không thấy gì cả nên đổi sang scan từ 1 - 20000 port đầu thì kết quả là có port 6379 đang mở:

![](https://i.imgur.com/lryH1js.png)

*Đáp án là: 6379*

---
## Task 2 <a name="t2"></a>

Dựa theo thông tin nmap scan thì service đang chạy ở port 6379 là redis:

![](https://i.imgur.com/Ex5XhAp.png)

*Đáp án là: redis*

---
## Task 3 <a name="t3"></a>

> Redis là 1 kho lưu trữ dữ liệu in-memory, thường được sử dụng như 1 cơ sở dữ liệu phân tán chứa các cặp key-value. Các bạn có thể xem thêm ở đây: https://en.wikipedia.org/wiki/Redis

*Đáp án là: In-memory Database* 

---
## Task 4 <a name="t4"></a>

> Program giúp chúng ta tương tác với redis server thông qua terminal là redis-cli. Các bạn có thể tham khảo syntax tại đây: https://redis.io/docs/manual/cli/

*Đáp án là: redis-cli*

---
## Task 5 <a name="t5"></a>

> Flag để chỉ định hostname là '-h'

![](https://i.imgur.com/iSZP39k.png)

*Đáp án là: -h*

---
## Task 6 <a name="t6"></a>

Để trả lời câu hỏi này, các bạn cần connect vào redis server trên target machine với câu lệnh như sau:

```
redis-cli -h <target-ip> -p 6379
```

![](https://i.imgur.com/f1lNCPz.png)

Câu lệnh dùng để xem thông tin về server là info:

![](https://i.imgur.com/EvA2kwX.png)

> Các bạn có thể tham khảo thêm syntax cảu redis-cli ở đây: https://www.tutorialspoint.com/redis/redis_commands.htm#:~:text=To%20start%20Redis%20client%2C%20open,you%20can%20run%20any%20command.&text=In%20the%20above%20example%2C%20we,server%20is%20running%20or%20not.

*Đáp án là: info*

---
## Task 7 <a name="t7"></a>

Dựa vào câu lệnh info, chúng ta thấy version của redis server sẽ là 5.0.7

![](https://i.imgur.com/HXpUqL1.png)

*Đáp án là: 5.0.7*

---
## Task 8 <a name="t8"></a>

> Câu lệnh để chọn database mong muốn trên redis server là select

![](https://i.imgur.com/Bxdlm8B.png)

*Đáp án là: select*

---
## Task 9 <a name="t9"></a>

Số keys bên trong database với index 0 là 4. Để có được thông tin số key trong database với index, ta sử dụng lần lượt các câu lệnh sau:

```
SELECT <index>
```

> Chọn index trên database

```
DBSIZE
```

> Show size của database, cũng chính là total keys

![](https://i.imgur.com/RIW3xlF.png)

Dựa theo hint thì ở phần Keyspace trong output của câu lệnh info cũng có đề cập:

![](https://i.imgur.com/wD2QV57.png)

*Đáp án là: 4*

---
## Task 10 <a name="t10"></a>

Để show ra toàn bộ keys của database mà không cần tới index, ta dùng 'KEYS *':

![](https://i.imgur.com/xqWEodH.png)

Đáp án là: KEYS * 


---
## Task 11 <a name="t11"></a>

Cuối cùng, để xem value của key mong muốn, ta dùng command GET:

```
GET <key>
```

![](https://i.imgur.com/jP2HczA.png)

*Đáp án là: 03e1d2b376c37ab3f5319922053953eb*
