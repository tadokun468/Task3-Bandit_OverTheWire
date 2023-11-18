## `Level 0->1` 
Yêu cầu : The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

1.Truy cập bằng lệnh : `ssh bandit.labs.overthewire.org -p 2220 -l bandit0`

2.Dùng lệnh `ls` ta thấy file tên `Readme`

3.Cuối cùng ta dùng lệnh `cat` ra để xem mật khẩu

Mật khẩu level : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 1->2`

## `Level 1->2` 
Yêu cầu như sau : The password for the next level is stored in a file called - located in the home directory.
1.Sau khi có được mật khẩu level 1 ta dùng lệnh `exit` để logout khỏi tài khoản bandit0 , ta tiếp tục truy cập cập bandit1 bằng lệnh :  `ssh bandit.labs.overthewire.org -p 2220 -l bandit1`

2.Sau đó dùng mật khẩu level 1 đã tìm được trước đó để truy cập và khi truy cập ta dùng lệnh `ls` thì thấy một file có tên là `-`

-  Thông thường nếu ta dùng lệnh `cat` để xem nội dung bên trong thì ta sẽ thấy rằng máy tính sẽ không chạy, dường như rằng nó đang đợi chúng ta nhập thêm một cái gì đó đại loại vậy. Ta ấn `Ctrl C` để ngừng chương trình.
-  **Lí do** bởi vì khi chúng ta sử dụng một câu lệnh nào đó, thì chúng ta có thể đưa các `option` vào câu lệnh thông qua `-` , nó được sử dụng để chỉ định một số tùy chọn cho lệnh.
-  Ví dụ khi ta truy cập server bằng lệnh `ssh bandit.labs.overthewire.org -p 2220 -l bandit1` 
-  Thì option ở đây là `-p` : Tùy chọn này đặt cổng (port) SSH mà ta muốn sử dụng.
- `-l` : Tùy chọn này xác định tên người dùng (username) mà ta muốn sử dụng để login vào máy chủ.
- **Giải quyết** : Ta có thể sử dụng đường dẫn tuyệt đối `cat /home/bandit1/-` hoặc `cat ./-` hoặc `cat < -` để chỉ ra là hãy cho nội dung của file `-` này hiển thị thông qua câu lệnh `cat`.
Mật khẩu : rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 2->3`

## `Level 2->3`
Yêu cầu : The password for the next level is stored in a file called spaces in this filename located in the home directory
Tiếp tục truy cập `ssh bandit.labs.overthewire.org -p 2220 -l bandit2` với mật khẩu ta vừa thu được trước đó.

1. Dùng lệnh `ls` thì ta thấy có một file tên là `spaces in this filename`. Và khi ta `cat` ra thì sẽ hiện thông báo lỗi như sau :
![Alt text](image.png)

2. **Lí do** là bởi vì trong file có chứa dấu khoảng trắng .
3. **Giải quyết** bằng cách đưa tên file vào dấu ngoặc kép như sau `"spaces in this filename"` hoặc `cat spaces\ in\ this\ filename`
![Alt text](image-1.png)
![Alt text](image-2.png)
Mật khẩu : aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 3->4`

## `Level 3->4`
Yêu cầu : The password for the next level is stored in a hidden file in the inhere directory.
Truy cập máy chủ `bandit.labs.overthewire.org -p 2220 -l bandit3` với mật khẩu ở level 2
1. Khi truy cập thành công ta dùng lệnh `ls` thì thấy có thư mục `inhere` . Ta truy cập vào thư mục `cd ỉnhere`. Sau đó dùng `ls` thì lại không thấy gì cả
2. **Lí do** là bởi vì file đã được ẩn đi .
3. **Giải quyết** bằng cách thêm các `option` tùy chọn vào lệnh `ls` như `ls -la` hoặc `ls-a1` để xem các tệp tin bị ẩn đi
![Alt text](image-3.png)
![Alt text](image-4.png) 
4. Cuối cùng ta nhìn thấy file `hidden` , ta thực hiện `cat .hidden` để xem mật khẩu
Mật khẩu : 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 4->5`
## `Level 4->5`
Yêu cầu : The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.
Truy cập `ssh bandit.labs.overthewire.org -p 2220 -l bandit4` với mật khẩu tìm được ở bài trước

1. Ta thực hiện các bước như trong hình
![Alt text](image-5.png)
2. **Nhận xét** ở đây có rất nhiều file , cách để kiểm tra nhanh thông tin file nào mà con người có thể đọc được ta có thể thực hiện thông qua lệnh `file`
3. Ví dụ : 
![Alt text](image-6.png)

4. Để áp dụng với tất cả các file ta thực hiện lệnh `file ./*`
![Alt text](image-7.png)

Từ đây ta có thể thấy được `-file07` chính là file chứa mật khẩu.
Cuối cùng ta chỉ cần `cat ./-file07` 
Mật khẩu tìm được là : lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 5->6`

## `Level 5->6`
Yêu cầu : The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
- human-readable
- 1033 bytes in size
- not executable

Truy cập `ssh bandit.labs.overthewire.org -p 2220 -l bandit5` với mật khẩu tìm được ở bài trước.

1. Ta thực hiện các bước cơ bản như sau thì thấy rằng có rất nhiều thư mục , và trong mỗi thư mục thì lại có nhiều file khác nhau.
![Alt text](image-8.png)

 Do đó rất khó để ta có thể tìm bằng tay
2. **Giải quyết** bằng cách dùng câu lệnh `find`
3. Thực hiện `find . -type f ! -executable -size 1033c`

- `.` : nghĩa là tìm kiếm sẽ bắt đầu từ thư mục hiện tại và tất cả các thư mục con của nó.
- `-type f`: một điều kiện được sử dụng để tìm kiếm các tệp (files) và không phải thư mục (folders).
- `! -executable`: Đây là một điều kiện phủ định (!) để loại trừ các tệp có quyền thực thi
- `-size 1033c`: Tìm kiếm các tệp có kích thước chính xác là 1033 byte.
![Alt text](image-9.png)
Đơn giản lúc này ta chỉ cần `cat` nó ra thôi
![Alt text](image-10.png)
Mật khẩu : P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 6->7`

## `Level 6->7`
Yêu cầu : The password for the next level is stored somewhere on the server and has all of the following properties:
- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit6` , với mật khẩu đã lấy được ở level trước.

1. Sau khi vào được máy chủ, ta dùng lệnh `ls` để kiểm tra thì bất ngờ là ta không thấy được gì cả.
![Alt text](image-11.png) 

2. Do đó ta thử di chuyển đến thư mục root bằng lệnh `cd /`
3. Tại thư mục này ta thử tìm kiếm bằng lệnh find
- `find . -type f -size 33c -user bandit7 -group bandit6` .
- user bandit7: Đây là điều kiện để chỉ tìm kiếm các tệp mà chủ sở hữu là "bandit7" 

- group bandit6: Đây là điều kiện để chỉ tìm kiếm các tệp mà nhóm sở hữu là "bandit6" 
Sau khi thực hiện được ta được như hình bên :
![Alt text](image-12.png)

4. Do xuất hiện quá nhiều thông báo lỗi trộn lẫn với kết quả cần tìm, nên chúng ta thêm `2>/dev/null` vào để lọc thông báo lỗi :
- `2>/dev/null`: Đây là phần của lệnh để chuyển hướng lỗi sang /dev/null (là một thư mục ảo), nơi mà lỗi sẽ bị "ném đi" và không hiển thị trên màn hình.

![Alt text](image-13.png)

Kết quả trả về chính là tệp chứa mật khẩu, bây giờ chúng ta chỉ cần `cat` nó ra là xong.
Mật khẩu : z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 7->8`

## `Level 7->8`
Yêu cầu : The password for the next level is stored in the file data.txt next to the word millionth
Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit7` , với mật khẩu đã lấy được ở level trước.
1. Đầu tiên `ls` để xem bên trong thư mục, thì thấy có file `data.txt`. Thử `cat` nó ra :

![Alt text](image-14.png)

2. Thì thấy có hàng ngàn dòng chữ khác nhau hiện ra, nhưng ta có keyword là chữ `millionth`
3. Do đó nhiệm vụ của ta là lọc ra chữ `millionth`
4. **Giải quyết** bằng câu lệnh `cat data.txt | grep millionth`
- `|`: Ký tự này được sử dụng để chuyển đầu ra (output) của lệnh bên trái thành đầu vào (input) của lệnh bên phải. Trong trường hợp này, đầu ra của cat data.txt (nội dung của tệp "data.txt") được chuyển đến làm đầu vào cho lệnh grep.
- `grep millionth`: lệnh grep được sử dụng để tìm kiếm các dòng chứa chuỗi "millionth" trong đầu vào mà nó nhận từ câu lệnh `cat data.txt`. Nếu có dòng nào chứa từ "millionth", nó sẽ hiển thị dòng đó trên màn hình.

![Alt text](image-15.png)

Mật khẩu : TESKZC0XvTetK0S9xNwm25STk5iWrBvP
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 8->8`

## `Level 8->9`
Yêu cầu : The password for the next level is stored in the file data.txt and is the only line of text that occurs only once
Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit8` , với mật khẩu đã lấy được ở level trước.
1. Dùng lệnh `ls` thì ta thấy file `data.txt`. Thử `cat` nó ra thì ta thấy tương tự như bài trước có hàng ngàn dòng chữ khác nhau.
![Alt text](image-16.png)
3. Đề bài nói rằng mật khẩu cần tìm là dòng chỉ xuất hiện đúng một lần duy nhất.
4. **Giải quyết** : Ta dùng lệnh `cat data.txt | uniq -u`
- `uniq -u`: lệnh uniq, được sử dụng để loại bỏ các dòng trùng lặp từ input. 
- Option `-u`chỉ định rằng chỉ các dòng không trùng lặp mới được hiển thị. 
Tuy nhiên nếu chúng ta chạy luôn thì kết quả vẫn sẽ chưa được hiển thị bởi vì lệnh này chỉ lọc những dòng trùng lặp ở cạnh nhau. 
![Alt text](image-17.png)

5. Do đó ta phải sắp xếp nó trước , sau đó mới lọc các dòng trùng lặp 
- `cat data.txt | sort | uniq -u`

![Alt text](image-18.png)

Mật khẩu : EN632PlfYiZbn3PhVK3XOGSlNInNE00t

Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 9->10`

## `Level 9->10`
Yêu cầu : The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.
Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit9` , với mật khẩu đã lấy được ở level trước.

1. Dùng lệnh `ls` thì ta thấy file `data.txt`. Thử `cat` nó ra ta thấy tương tự như bài trước  thì lần này hàng ngàn kí tự chúng ta không đọc được 
 
 ![Alt text](image-19.png)

Đề bài gợi ý rằng mật khẩu được bắt đầu bằng một vài kí tự `=` 
2. **Giải quyết** bằng cách dùng lệnh `strings data.txt | grep ==`
 - strings data.txt: Câu lệnh strings được sử dụng để trích xuất tất cả các chuỗi văn bản từ tệp "data.txt"
 ![Alt text](image-20.png)

Mật khẩu : G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 10->11`

## `Level 10->11`
Yêu cầu : The password for the next level is stored in the file data.txt, which contains base64 encoded data
Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit10` , với mật khẩu đã lấy được ở level trước.

1. Dùng lệnh `ls` thì ta thấy file `data.txt`. Thử `cat` nó ra ta thấy một chuỗi xuất hiện , được mã hóa bằng base64 (thường có dấu == ở cuối)
2. **Giải quyết** bằng lệnh `base64 -d data.txt`
- `-d`: Đây là một tùy chọn của lệnh base64, nó chỉ định rằng bạn đang thực hiện thao tác giải mã (decode). Nếu không có tùy chọn này, lệnh base64 sẽ mặc định mã hóa dữ liệu.

![Alt text](image-21.png)

Mật khẩu : 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 11->12`

## `Level 11->12` 
Yêu cầu : The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions
Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit11` , với mật khẩu đã lấy được ở level trước.

1. Dùng lệnh `ls` thì ta thấy file `data.txt`. Thử `cat` nó ra ta thấy một chuỗi được mã hóa ROT13 xuất hiện  

![Alt text](image-22.png)

2. **Giải quyết** ta dùng lệnh `tr` thực hiện thay thế các ký tự trong một chuỗi văn bản :
- `cat data.txt | tr 'n-z a-m N-Z A-M' 'a-m n-z A-M N-Z'`
- Giải thích : 
Thay thế cặp  'N-Z' thành 'A-M'
Thay thế cặp  'A-M' thành 'N-Z'
Thay thế cặp  'n-z' thành 'a-m'
Thay thế cặp  'a-m' thành 'n-z'

![Alt text](image-23.png)

Mật khẩu : JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 12->13`

## `Level 12->13`
Yêu cầu : The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit12` , với mật khẩu đã lấy được ở level trước.

1.  Dùng lệnh `ls` thì ta thấy file `data.txt`. Thử `cat` nó ra ta thấy một dãy các kí tự biểu diễn dưới dạng hexdump

![Alt text](image-24.png)

2. Ta phải giải mã file này thông qua câu lệnh `xxd -r <tên_file`
- `-r` có nghĩa là reverse nó lại
 
 ![Alt text](image-25.png)

3. Tuy nhiên reverse như thế này thì chưa được, nó vẫn chỉ là một dạng file nào đó thôi. Ta sẽ phải tạo và lưu trữ nó vào một file nào đó. Ví dụ : `xxd -r data.txt > flag`

![Alt text](image-26.png)

Tuy nhiên ta bị từ chối truy cập vì chúng ta không thể chỉnh sửa bất cứ thứ gì ở trong thư mục home directory (chỉ có quyền đọc và thực thi). Chúng ta chỉ có quyền thực hiện chỉnh sửa với thư mục temporary (tmp)

4. Do đó ta dùng lệnh `mktemp -d` để tạo một thư mục tạm thời
- `-d`: Đây là một tùy chọn của lệnh mktemp và nó chỉ định rằng chúng ta muốn tạo một thư mục tạm thời. Nếu dụng mktemp mà không có tùy chọn `-d`, nó sẽ tạo một tệp tạm thời thay vì thư mục.

![Alt text](image-27.png)

Ta coppy thư mục `data.txt` sang thư mục vừa tạo bằng lệnh `cp ~/data.txt .`

5. Ta thực hiện lại thao tác tương tự như bước 3 , và tiến hành kiểm tra file đó bằng lệnh `file file_name` , thì ta thấy file dang được nén dưới dạng gzip. Do đó ta phải giải nén file này ra

6. Tuy nhiên trước khi giải nén , ta phải đổi tên file để nó có đúng định dạng gzip bằng lệnh `mv file_name file_name.gz` . Sau đó giải nén nó bằng lệnh `gunzip file_name.gz`.
Vì file này được nén nhiều lớp nên ta phải thực hiện cùng một thao tác trên nhiều lần mới ra được flag cần tìm :

![Alt text](image-28.png)
![Alt text](image-29.png)
Các loại nén tệp dược dùng thêm ngoài gzip :
- `bzip2` : Giải nén bằng lệnh `bzip2 -d file_name.bz2`
- `tar` : Giải nén bằng lệnh `tar -xvf file_name`

Mật khẩu : wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới level `13->14`

## `Level 13->14`
Yêu cầu : The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit13` , với mật khẩu đã lấy được ở level trước.

1. Như thường lệ ta dùng `ls` để xem có gì , và in thử nó ra

![Alt text](image-30.png)

Thì ở đây ta thấy có một file tên là `sshkey.private` chứa đoạn mã khóa RSA Private Key. Đoạn mã này được bắt đầu bằng "-----BEGIN RSA PRIVATE KEY-----" và kết thúc bằng "-----END RSA PRIVATE KEY-----". Đây là một khóa cá nhân RSA, thường được sử dụng trong việc xác thực và mã hóa trong giao thức SSH. 
Đây là chính là key để ta có thể mở bandit14 

2. Ta thử `cd /etc/bandit_pass/` đến thư mục này và `ls`

![Alt text](image-31.png)

Đây chính là những file chứa mật khẩu, tuy nhiên chúng ta chỉ đọc được của bandit13 mà thôi, do vậy chúng ta phải đăng nhập hệ thống thông qua bandit14 sử dụng `sshkey.private` lúc nãy.


3. Bây giờ ta dùng `cd ~` để trở về thư mục có chứa `sshkey.private` , và sử dụng ssh để dăng nhập user là bandit14 với sshkey trên .
4. Truy cập đến cùng một vị trí `localhost` :
- `ssh localhost -p 2220 -i sshkey.private -l bandit14`

5. Sau khi thực hiện như trên , ta đã có thể đăng nhập vào `bandit14` và việc đơn giản lúc này ta chỉ cần làm như sau :
![Alt text](image-32.png)

Mật khẩu : fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 14->15`

## `Level 14->15`
Yêu cầu : The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.
Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit14` , với mật khẩu đã lấy được ở level trước.

Với yêu cầu đơn giản như trên chúng ta chỉ cần dùng câu lệnh netcat `nc` để truy cập và nhập mật khẩu đã lấy được ở level trước đó như sau :

- `nc localhost 30000`

![Alt text](image-33.png)

Mật khẩu : jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Dùng lệnh `Ctrl C` để ngừng, và lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 15->16`

## `Level 15->16`
Yêu cầu : The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.
- Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit15` , với mật khẩu đã lấy được ở level trước.

1. Ở bài này thay vì sử dụng `netcat` thì đề bài yêu cầu chúng ta sử dụng `SSL encryption`
2. Do đó cú pháp như sau : `openssl s_client -connect localhost:30001`
3. Sau đó chúng ta nhập mật khẩu của level trước vào, kết quả chúng ta sẽ nhận được mật khẩu ở level hiện tại.
![Alt text](image-34.png) 
Mật khẩu: JQttfApK4SeyHwDlI9SXGR50qclOAil1
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 16->17`

## `Level 16->17`
Yêu cầu : The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit16` , với mật khẩu đã lấy được ở level trước.

1. Với đề bài trên thì ta sẽ sử dụng một công cụ rất thông dụng trong giới An Toàn Thông Tin đó chính là `nmap`. Công cụ này sẽ hỗ trợ việc quét các cổng (port), nó sẽ gửi đến hàng loạt các yêu cầu phản hồi cho tất cả các port, xem xét port nào lắng nghe và phản hồi lại.
2. Sử dụng câu lệnh ` nmap -A -p 31000-32000 localhost`
- `-A`: Đây là tùy chọn để bật chế độ "aggressive scan" trong Nmap, cho phép Nmap thực hiện các kiểm tra mạng một cách toàn diện, bao gồm việc xác định hệ điều hành, phiên bản phần mềm, dịch vụ đang chạy trên cổng và nhiều thông tin khác về máy chủ.
3. Sau khi chạy lệnh ta đợi một xíu để quét các cổng , kết quả sẽ trả về như hình
![Alt text](image-35.png)

4. Trong hình trên thì sự chú ý của ta đã va phải vào `ssl/unknown` của port `31790`. Port này là có khả năng nhất , bởi vì các cổng khác đang chạy dịch vụ `echo` (cho phép gửi dữ liệu đến cổng và nhận lại chính dữ liệu đó). 
5. Vậy ta đã tìm được port trong số các port từ 31000 đến 32000 , bây giờ chúng ta thử truy cập đến port này và xem kết quả trả về như thế nào thông qua câu lệnh `openssl s_client -connect localhost:31790 ` và gửi mật khẩu ở level trước vào , kết quả trả về như sau :
![Alt text](image-36.png)

Một khóa RSA giống như bài trước , do vậy ta xử lí các bước tương tự như level trước:

- Đầu tiên cho khóa key vào một file 
- Vì không thể thực hiện chỉnh sửa trên thư mục home nên ta phải tạo ra một thư mục tạm thời bằng lệnh `mktemp -d` rồi `cd` vào thư mục tạm thời này , tạo file mới rồi cho key vào.
![Alt text](image-37.png)

6. Vì `sshkey` là một key chứa thông tin riêng tư do vậy ta phải thay đổi quyền truy cập của tệp bằng lệnh `chmod 600 file_key_name`
- Số 6 đại diện cho quyền đọc (read) và ghi (write) chỉ áp với chủ sở hữu.
- Số 0 đại diện cho không có quyền đọc, ghi, hoặc thực thi nào được các nhóm khác (group) và người dùng khác (others).
- Note : nếu không thay đổi quyền truy cập thành riêng tư thì sẽ có thông báo lỗi như sau :
![Alt text](image-38.png)

7. Sau khi đã thay đổi quyền truy cập cho `sshkey`, lúc này cho có thể dùng câu lệnh `ssh bandit.labs.overthewire.org -p 2220 -i file_key_name -l bandit17` để kết nối.
8. Sau khi kết nối thành công vào bandit17. Hãy cùng nhớ lại những bài trước (level 13->14) thì ta đã được biết rằng mật khẩu chính thức được lưu trữ ở thư mục `/etc/bandit_pass/` . Do vậy chúng ta đơn giản là `cd /etc/bandit_pass/` và `cat bandit17` thì đã có được mật khẩu một cách dễ dàng.
![Alt text](image-40.png)

Mật khẩu : VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 17->18`

## `Level 17->18`
Yêu cầu : There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new
- NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit17` , với mật khẩu đã lấy được ở level trước.

1. Để tìm kiếm dòng duy nhất bị thay đổi giữa `password.old` và `password.new` , thì ta sẽ rất khó để chúng ta có thể tìm được bằng mắt thường 
2. Do vậy chúng ta có câu lệnh `diff` để tìm sư khác biệt giữa hai file như sau `diff password.old password.new`
![Alt text](image-41.png)

Mật khẩu : hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 18->19`.

## `Level 18->19`
Yêu cầu : The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit18` , với mật khẩu đã lấy được ở level trước.

1. Ở bài này có một điều thú vị là ngay khi ta vừa đăng nhập máy chủ thành công thì lập tức bị logout do `.bashrc` đã bị chỉnh sửa. Tập tin `.bashrc` là một tập tin cấu hình cho shell Bash trong hệ thống Linux và Unix. Khi một người dùng đăng nhập vào hệ thống hoặc mở một cửa sổ terminal mới, Bash sẽ đọc và thực thi nội dung của tập tin `.bashrc`.

2. Bình thường khi ta thực hiện `ssh` để kết nối tới máy chủ , thì chúng ta sẽ được cung cấp shell (Bash) mặc định và Bash sẽ đọc và thực thi nội dung của tập tin .bashrc.
3. Nhưng ở đây `.bashrc` đã bị chỉnh sửa để logout ra lập tức , do vậy chúng ta sẽ tạm thời vô hiệu hóa một số phần cụ thể của `.bashrc` bằng cách sử dụng các lựa chọn như --noprofile, --norc, --noediting để tắt một số tính năng cụ thể trong Bash. Ta sẽ thử câu lệnh như sau: `ssh bandit.labs.overthewire.org -p 2220 -l bandit18 "bash --noprofile"` 
- Giải thích : Sau khi kết nối thành công, chúng ta sẽ chạy lệnh bash --noprofile. Lệnh này sẽ khởi chạy shell bash mà không tải hồ sơ người dùng.
4. Ở đây ta `ls` thì thấy file `readme` . Thực hiện `cat` để lấy mật khẩu.
![Alt text](image-42.png)

Mật khẩu : awhqfNnAbc1naukrpqDYcF95h7HoMTrC
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 19->20`.

## `Level 19->20`
Yêu cầu : To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit19` , với mật khẩu đã lấy được ở level trước.

1. Thực hiện `ls` để xem thì ta thấy có một file tên là `bandit20-do`. Check xem nó là cái gì , sử dụng như thế nào:
 ![Alt text](image-44.png)
Đây chính là file cho phép ta chạy thực thi dưới quyền của bandit20.
1. Và như đã biết ở các level trước thì mật khẩu của bandit20 sẽ được lưu trữ ở `/etc/bandit_pass/bandit20`
2. Do vậy chúng ca chỉ cần `cat` với quyền của bandit20 như sau:`./bandit20-do cat /etc/bandit_pass/bandit20`
![Alt text](image-43.png)
Mật khẩu : VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 20->21`.

## `Level 20->21`
Yêu cầu : There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).
- NOTE: Try connecting to your own network daemon to see if it works as you think

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit20` , với mật khẩu đã lấy được ở level trước.

1. Đầu tiên ta `ls` thì thấy có một file tên là `suconnect`.
Ta thử check xem file `suconnect` :
![Alt text](image-45.png)

Dựa theo đó thì ta cần một kết nối với một cổng khác , sau đó từ cổng vừa kết nối ta gửi ngược lại mật khẩu cho cổng ban đầu .

2. Ta tạo kết nối một cổng để lắng nghe `netcat -nlvp 8888`
- `n` netcat sẽ sử dụng địa chỉ IP thay vì tên miền khi kết nối với máy chủ.
- `l` là listen (khởi tạo máy chủ)
- `v` : in ra thông tin khi có kết nối
- `p` là port để sử dụng kết nối. Ở đây chúng ta sẽ sử dụng port chẳng hạn như 8888
3. Kết nối với port 8888 vừa khởi tạo bằng lệnh `./suconnect 8888`
4. Dán mật khẩu của level trước vào cổng ta vừa tạo (port 8888)
Kết quả sẽ như hình : 
![Alt text](image-46.png)
Mật khẩu : NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 21->22`.

## `Level 21->22`
Yêu cầu : A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.
Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit21` , với mật khẩu đã lấy được ở level trước.

1. Đầu tiên di chuyển đến thư mục `/etc/cron.d/`
![Alt text](image-47.png)
2. Ta `cat` file `cronjob_bandit22`
![Alt text](image-48.png)
3. Tiếp tục `cat /usr/bin/cronjob_bandit22.sh`
![Alt text](image-49.png) 
4. Từ ảnh trên cho thấy mật khẩu của bandit22 được lưu trữ ở `/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`. Vậy nhiệm vụ của ta là chỉ cần `cat` file này ra là xong 
![Alt text](image-50.png)

Mật khẩu : WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 22->23`.

## `Level 22->23`
Yêu cầu : A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

- NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.
Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit22` , với mật khẩu đã lấy được ở level trước.

1. Bài này tương tự như bài `level 21->22` , đầu tiên di chuyển đến thư mục `/etc/cron.d/`
2. Ta `cat` file `cronjob_bandit23`
3. Tiếp tục `cat /usr/bin/cronjob_bandit23.sh` để xem bash script
![Alt text](image-51.png)

5. Đầu tiên ta `echo $(whoami)` để xem thử , thì kết quả như hình
![Alt text](image-52.png)
Ta thấy rằng do ta đang chạy dưới quyền của bandit22 để thực hiện câu lệnh trên , kết quả trả về là user hiện tại.
Mà đoạn bash trên được chạy dưới quyền của bandit23 cho nên biến `myname = bandit23`
6. Lấy `bandit23` vào giá trị của biến `myname`ta được giá trị của biến `mytarget` như sau :
![Alt text](image-53.png)
7. Cuối cùng thay giá trị của biến `mytarget` vào ta được mật khẩu
![Alt text](image-54.png)
Mật khẩu : QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 23->24`.

## `Level 23->24`
Yêu cầu : A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.
- NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!
- NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit23` , với mật khẩu đã lấy được ở level trước.

1. Bài này tương tự như 2 bài trước , đầu tiên di chuyển đến thư mục `/etc/cron.d/`
2. Ta `cat` file `cronjob_bandit24`
3. Tiếp tục `cat /usr/bin/cronjob_bandit24.sh` để xem bash script
![Alt text](image-55.png)

- Hiểu đơn giản thì đoạn script này , đang duyệt qua tất cả các tệp tin và thư mục trong `/var/spool/$myname/foo` (trừ thư mục `.` và `..`). Biến `$myname` có giá trị là `bandit24` bởi vì đoạn script này đang được chạy dưới quyền của `bandit24`.
- `owner="$(stat --format "%U" ./$i)"` dòng này đang lấy ra tên của chủ sở hữu của tệp tin. Nếu chủ sở hữu mà là `bandit13` thì sẽ chạy thực thi file đó trong 60 giây.
- Do vậy ta cần tạo một file script để thực hiện chức năng lấy mật khẩu của `bandit24` tại thư mục người dùng của `bandit23` , sau đó đưa file vào thư mục `/var/spool/bandit24/foo` để nó thực thi dưới quyền của `bandit24`
4. Ta tạo một file script `get_flash.sh` và một file `flag` để nhận mật khẩu (ở thư mục `tmp` bởi vì chúng ta chỉ có quyền chỉnh sửa ở thư mục `tmp`). Dĩ nhiên là ta phải cấp quyền đọc, ghi, thực thi cho tất cả người dùng khác bằng lệnh `chmod 777` 
![Alt text](image-59.png)
![Alt text](image-60.png)
5. Sau đó ta sao chép file `get_flash.sh` vào thư mục `/var/spool/bandit24/foo` bằng lệnh `cp get_flash.sh /var/spool/bandit24/foo`
6. Ta biết rằng khi thực thi xong thì file sẽ bị xóa , cho nên nếu chúng ta thực hiện lệnh `cat` mà ra kết quả như trên ảnh thì chứng tỏ rằng đã thực thi thành công.
![Alt text](image-62.png)
![Alt text](image-61.png)
Mật khẩu : VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 24->25`.

## `Level 24->25`
Yêu cầu : A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.
You do not need to create new connections each time

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit24` , với mật khẩu đã lấy được ở level trước.

1. Đầu tiên ta thử `nc localhost 30002` 
![Alt text](image-75.png)
Ở đây ta cần nhập mật khẩu ở level trước với mã pin chạy từ `0000` đến `9999`. Do còn có thời gian `Timeout` nên việc chúng ta làm thủ công là rất khó. Do vậy chúng ta phải viết một vòng lặp để thực hiện việc gửi đi các hoán vị trong đoạn từ `0000` đến `9999`.

2. Ta sẽ viết vòng lặp như sau `for i in {0000..9999}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002`. Mỗi lần vòng lặp chạy, nó sẽ tạo một dòng output và chuyển ngay lập tức đến nc localhost 30002.
![Alt text](image-72.png)
![Alt text](image-68.png)

Giả sử mật khẩu của chúng ta không nằm ở dưới cùng, mà nằm ở chính giữa những thông báo Wrong thì sao.
Để giải quyết chúng ta chỉ cần ghi vào 1 file (ví dụ : traloi.txt) .

![Alt text](image-73.png)

Sau đó lọc ra những dòng giống nhau là được, cùng nhớ lại thì ta đã từng làm ở `level 8->9`. Câu lệnh sẽ được viết như sau : `cat traloi.txt | sort | uniq -u`

![Alt text](image-74.png)

Lưu ý : Để tạo ghi file thì chúng ta phải thực hiện ở thư mục `tmp` nhé . Cách tạo là `mktemp -d`

Mật khẩu : p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 25->26`.

## `Level 25->26`
Yêu cầu : Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit25` , với mật khẩu đã lấy được ở level trước.

1. Đầu tiên ta `ls` xem thử có gì , thì thấy được một `bandit26.sshkey` .
![Alt text](image-76.png)
2. Do vậy chúng ta có thể đăng nhập vào `bandit26` một cách dễ dàng thông qua câu lệnh `ssh localhost -p 2220 -i bandit26.sshkey -l bandit26`.
Nhưng ngay khi đăng nhập thành công thì `bandit26` lập tức bị đóng lại 
![Alt text](image-77.png)

3. Theo đề bài thì the shell cho bandit26 không phải là một `/bin/bash`. Nên ta thử kiểm tra trong thư mục `/etc` xem thử the shell mặc định cho `bandit26` thử là cái gì.
- Thông tin về mỗi người dùng được lưu trữ dưới dạng một dòng trong tập tin /etc/passwd, với các trường được ngăn cách bằng dấu hai chấm `:`. Các trường thông tin bao gồm tên người dùng, mật khẩu (thường là 'x') , UID (User ID), GID (Group ID), thông tin về người dùng, thư mục người dùng và shell mặc định
![Alt text](image-78.png)  
Xem shell mặc định của `bandit26` là gì
![Alt text](image-79.png)
Thử xem nội dung bên trong 
![Alt text](image-80.png)

Dòng mà ta cần đặc biệt quan tâm ở đây là `exec more ~/text.txt`
- Dùng `exec` trong một script shell giống như việc thay thế tiến trình shell hiện tại bằng một chương trình hoặc script khác.
- `more` là một chương trình hiển thị văn bản trong môi trường dòng lệnh của Unix và các hệ thống tương tự. Nó được sử dụng để xem nội dung của tệp tin 1 trang cho phép người dùng dừng lại, cuộn lên và xuống, và thậm chí tìm kiếm trong văn bản.
- `exec more ~/text.txt` có nghĩa là thay thế shell hiện tại bằng chương trình more và mở tệp tin ~/text.txt để xem nội dung. 
- Điều này có tác dụng làm cho shell script kết thúc khi chương trình more kết thúc, chính vì vậy để shell (Bash) không lập tức bị đóng lại thì ta phải cố làm cho `more` hoạt động bằng cách thu nhỏ màn hình lại.
![Alt text](image-82.png)
![Alt text](image-83.png)
- Tiếp tục tham khảo trong `man more` thì ta có thể mở một trình soạn thảo văn bản (thường là vi hoặc vim) để xem và chỉnh sửa nội dung của tệp tin hiện tại bằng cách nhấn phím "v" (viết tắt của "view").
![Alt text](image-81.png)
4. Bây nhấn phím `v`

![Alt text](image-84.png)
Ta đã vào được bên trong `vi`
5. Nhiệm vụ của ta là đọc mật khẩu từ `/etc/bandit_pass/bandit26` thông qua `:r` được sử dụng để đọc (read) nội dung từ một tệp tin vào bên dưới hoặc trên dòng hiện tại. Hoặc ta cũng có thể `:set shell=/bin/bash` và `:sh` để thực thi câu lệnh chuyển sang môi trường shell xong đó `cat /etc/bandit_pass/bandit26` để lấy mật khẩu.
6. Để thực hiện thì ta cần làm theo các bước sau :
- Nhấn Esc để chuyển sang chế độ command mode.
- Gõ :r tên_tệp_tin và nhấn Enter.
![Alt text](image-85.png)
Nhấn `Enter` và ta có được mật khẩu
![Alt text](image-86.png)

Mật khẩu : c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
Sử dụng mật khẩu này tiếp tục tới `level 26->27`.

## `Level 26->27`
Yêu cầu : Good job getting a shell! Now hurry and grab the password for bandit27!
Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit26` , với mật khẩu đã lấy được ở level trước.

1. Thì theo bài trước thì ta đã biết rằng `bandit26` sẽ bị đóng ngay lập tức cho nên ta sẽ thực hiện tương tự để vào trình soạn thảo văn bản `vi`.
2. Ở đây thì mình sẽ đổi sang môi trường shell bằng câu lệnh `:set shell=/bin/bash` mình đã nhắc đến trong bài trước.
![Alt text](image-87.png)
![Alt text](image-88.png)

3. Ta `ls` để xem bên trong :
![Alt text](image-89.png)

Thấy file `bandit27-do` ta liên tưởng ngay tới `level 19->20` ta từng làm bài tương tự , còn file `text.txt` thì không có gì đặc biệt
Nhận xét : bài này kết hợp giữa `level 25->26` và `level 19->20`

4. File `bandit27-do` thì chính là file cho phép ta chạy thực thi dưới quyền của `bandit27`. Mà mật khẩu của `bandit27` thì được lưu trữ ở `/etc/bandit_pass/bandit27`. Cho nên ta chỉ cần `cat` nó ra là xong.
 
Mật khẩu : YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
Sử dụng mật khẩu này tiếp tục tới `level 27->28`.

## `Level 27->28`
Yêu cầu : 
- There is a git repository at ssh://bandit27-git@localhost/home/bandit27-git/repo via the port 2220. The password for the user bandit27-git is the same as for the user bandit27.
- Clone the repository and find the password for the next level.

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit27` , với mật khẩu đã lấy được ở level trước.

1. Theo đề bài thì ta phải sao chép (clone) một repository Git từ địa chỉ được cung cấp. Thông qua câu lệnh `git clone` ta có thể tạo ra một bản sao đầy đủ của repository với toàn bộ lịch sử commit và các nhánh.
2. Bởi vì ta không được phép tạo cái gì ở trong thư mục homedirectory này. Nên đầu tiên thì ta tạo một thư mục `tmp` để chứa tệp mà ta clone về bằng câu lệnh `mktemp -d` và `cd` vào thư mục đó.
3. Nhập câu lệnh `git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo` và `Enter` , sau đó nhập mật khẩu của level trước.
4. Sau khi tải thành công , ta di chuyển vào thư mục vừa tải , kiểm tra và in ra mật khẩu như sau :
![Alt text](image-90.png)

Mật khẩu : AVanL161y9rsbcJIsFHuw35rjaOM19nR
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 28->29`.

## `Level 28->29`
Yêu cầu :
- There is a git repository at ssh://bandit28-git@localhost/home/bandit28-git/repo via the port 2220. The password for the user bandit28-git is the same as for the user bandit28.
- Clone the repository and find the password for the next level.

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit28` , với mật khẩu đã lấy được ở level trước.

1. Các bước truy cập ta làm tương tự như `level 27->28` : Đầu tiên tạo ra một thư mục tạm thời thông qua câu lệnh `mktemp -d` sau đó `cd` vào và tiếp tục nhập câu lệnh `git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo` và `Enter` , sau đó nhập mật khẩu của level trước. Sau khi tải thành công , ta di chuyển vào thư mục vừa tải , kiểm tra và `cat` ra thử :
![Alt text](image-91.png)

2. Ở đây thì mật khẩu đã bị ẩn đi , thế thì ta kiểm tra cái file này đã từng bị chỉnh sửa rồi hay chưa (commit) thông qua câu lệnh `git log`
![Alt text](image-92.png)

Thì ta thấy ở trong này có 3 commit

3. Ta thử chuyển qua lần lượt 2 nhánh commit trước đó bằng câu lệnh `git checkout tên_conmmit` :
-  `git checkout f08b9cc63fa1a4602fb065257633c2dae6e5651b` 
4. Sau đó `ls` xem thử bên trong và thử `cat` ra 
![Alt text](image-93.png)

Vậy là ta đã có được mật khẩu

Mật khẩu : tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 29->30`.

## `Level 29->30`
Yêu cầu : 
- There is a git repository at ssh://bandit29-git@localhost/home/bandit29-git/repo via the port 2220. The password for the user bandit29-git is the same as for the user bandit29.
- Clone the repository and find the password for the next level.

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit29` , với mật khẩu đã lấy được ở level trước.


1. Các bước truy cập ta làm tương tự như 2 level trước : Đầu tiên tạo ra một thư mục tạm thời thông qua câu lệnh `mktemp -d` sau đó `cd` vào và tiếp tục nhập câu lệnh `git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo` và `Enter` , sau đó nhập mật khẩu của level trước. Sau khi tải thành công , ta di chuyển vào thư mục vừa tải , kiểm tra và `cat` ra thử :
![Alt text](image-94.png)
Nhận xét :  <no passwords in production!>
Do vậy ta sẽ thử chuyển sang các nhánh khác trong repo.

2. Đâu tiên ta list tất cả các nhánh ra bằng câu lệnh `git branch -a`
![Alt text](image-95.png)

3. Sau đó check lần lượt :
![Alt text](image-96.png)

Vậy là ở lần check đầu tiên ta đã tìm được mật khẩu

Mật khẩu : xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 30->31`.

## `Level 30->31`
Yêu cầu : 
- There is a git repository at ssh://bandit30-git@localhost/home/bandit30-git/repo via the port 2220. The password for the user bandit30-git is the same as for the user bandit30.
- Clone the repository and find the password for the next level.

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit30` , với mật khẩu đã lấy được ở level trước.


1. Các bước truy cập ta làm tương tự như 3 level trước : Đầu tiên tạo ra một thư mục tạm thời thông qua câu lệnh `mktemp -d` sau đó `cd` vào và tiếp tục nhập câu lệnh `git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo` và `Enter` , sau đó nhập mật khẩu của level trước. Sau khi tải thành công , ta di chuyển vào thư mục vừa tải , kiểm tra và `cat` ra thử :
![Alt text](image-97.png)
Và đó chính là cú lừa

2. Đầu tiên ta kiểm tra xem thử file này có commit nào không 
![Alt text](image-98.png)
Đây là commit đầu tiên luôn

3. Kiểm tra nhánh
![Alt text](image-99.png)
Cũng không có gì đặc biệt
4. Ngoài ba cái trên thì trong Git, tag là một cách để đánh dấu một commit cụ thể trong lịch sử mã nguồn. Việc sử dụng tag giúp xác định rõ ràng các phiên bản hoặc các điểm quan trọng trong lịch sử phát triển của dự án. Tag thường được sử dụng cho việc định danh các bản phát hành (releases).
5. Cho nên ta thử kiểm tra `git tag`
![Alt text](image-100.png)
Vậy ta đã tìm được mật khẩu 

Mật khẩu : OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 31->32`.

## `Level 31->32`
Yêu cầu : 
- There is a git repository at ssh://bandit31-git@localhost/home/bandit31-git/repo via the port 2220. The password for the user bandit31-git is the same as for the user bandit31.
- Clone the repository and find the password for the next level.

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit31` , với mật khẩu đã lấy được ở level trước.

1. Các bước truy cập ta làm tương tự như 4 level trước : Đầu tiên tạo ra một thư mục tạm thời thông qua câu lệnh `mktemp -d` sau đó `cd` vào và tiếp tục nhập câu lệnh `git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo` và `Enter` , sau đó nhập mật khẩu của level trước. Sau khi tải thành công , ta di chuyển vào thư mục vừa tải , kiểm tra và `cat` ra thử :
![Alt text](image-101.png)
Nhận xét : Ở đây thì ta thấy rõ là rất tường minh rồi , nhiệm vụ của chúng ta là `push` một file có tên là key.txt lên Branch : master , có nội dung là `May I come in?`

2. Các bước thực hiện như sau : 
![Alt text](image-102.png)
Note : `-f` (force-add) bắt buộc cho lên đã , không cần kiểm tra . Git thêm (add) một tệp tin hoặc thư mục vào danh sách theo dõi mà không quan tâm đến các quy tắc kiểm tra hay các loại tệp tin được liệt kê trong `.gitignore`
Có yêu cầu nhập mật khẩu thì ta nhập mật khẩu của level trước đó.

Kết quả trả về như sau :
![Alt text](image-104.png)

Mật khẩu : rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
Dùng lệnh `exit` để logout và sử dụng mật khẩu này tiếp tục tới `level 32->33`.

## `Level 32->33`
Yêu cầu : After all this git stuff its time for another escape. Good luck!

Ta truy cập máy chủ : `ssh bandit.labs.overthewire.org -p 2220 -l bandit32` , với mật khẩu đã lấy được ở level trước.

1. Sau khi đăng nhập thành công thì ta được cung cấp cho một upershell , nó chuyển đổi tất cả kí tự chữ cái sang chữ in hoa
![Alt text](image-105.png)

Để chuyển đổi về lại shell mặc định của hệ thống thì ta phải nhắc dến một giá trị `$0` . 

Bản chất của `$0` là cung cấp thông tin về tên của chính shell hiện tại hoặc tên của chương trình được thực thi. Khi bạn chạy một script, giá trị của $0 thường là tên của script đó.

Nếu ta `echo $0` thì kết quả trả về `-bash`

![Alt text](image-106.png)

`-bash`, điều này thường đều ngụ ý rằng bạn đang chạy một phiên bản của shell Bash với tùy chọn "login shell". "Login shell" được kí hiệu bằng dấu gạch ngang (`-`) ở đầu dòng lệnh.

2. Do vậy khi ta nhập `$0` thì hệ thống sẽ thực hiện login về shell mặc định của hệ thống :
![Alt text](image-107.png)
3. Kiểm tra xem ta đang ở dưới tên của user nào :
![Alt text](image-108.png)

4. Thực hiện lấy mật khẩu :
![Alt text](image-109.png)

Mật khẩu : odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
Dùng lệnh `exit` và `Ctrl C` để thoát và tiếp tục tới level tiếp theo cũng là level cuối cùng

## `Level 33->34`

Truy cập `ssh bandit.labs.overthewire.org -p 2220 -l bandit33` 
Với mật khẩu là `odHo63fHiFqcWWJG9rLiLDtPm45KzUKy`

![Alt text](image-110.png)

**Congratulations on solving the last level of this game!**

**Yeeeeeeeeeeeeeee**


`1:04 am - 10/11/2023`
