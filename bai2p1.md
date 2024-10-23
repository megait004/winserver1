# 2.1. Nâng cấp máy chủ Windows Server 2012 lên Domain Controller và Join Domain
**Chú ý**: Trước khi làm bài này, tất cả card mạng của máy server1 của bài 1 các bạn xoá hết đi cho mình nhé rồi thêm lại card mạng như ở bài 1 đã học.
- xoá card NIC Teaming các bạn làm như sau:
  - Vào phần server manager vào all server nhân chuột phải như trong ảnh và nhấn vào config NIC Teaming.
  ![Hiển thị](./b2p1images/1.png)
- Click chuột phải vào chọn delete.
  ![Hiển thị](./b2p1images/2.png)
- Tiếp theo chọn phần setting của máy server
  ![Hiển thị](./b2p1images/3.png)
  - Xoá các card mạng của máy server , nhấn chữ "remove" và sau đó nhấn oke
  ![Hiển thị](./b2p1images/4.png)
- Thêm lại card mạng như ở bài 1 đã học. **_Chú ý_:**
  - Đảm bảo cả 2 máy sử dụng cùng một VMnet.
  - Của mình là VMnet0.
  ![Hiển thị](./b2p1images/5.png)


## Tiếp theo bạn cấu hình ip cho card mạng của máy server1 và card mạng của máy win10 như sau :
- Bảng ip của mình như sau :
  ![Hiển thị](./b2p1images/6.png)
- Cấu hình ip cho card mạng của máy server1 như sau :
  ![Hiển thị](./b2p1images/7.png)
- Cấu hình ip cho card mạng của máy win10 như sau :
  ![Hiển thị](./b2p1images/8.png)

**_Chú ý_:** Các bạn ping thử từ win10 đến ip server1 xem nó được chưa sẽ làm bước tiếp theo nhé.
### Thực hiện cài đặt dịch vụ Active Directory Domain Services trên máy server1
- Bạn vào máy server1 vào phần server manager nhẫn vào manage trên thanh công cụ.Chọn add roles and features.
  ![Hiển thị](./b2p1images/9.png)
- Bước này các bạn chọn NEXT
  ![Hiển thị](./b2p1images/10.png)
- Bước này cũng Next nhé
  ![Hiển thị](./b2p1images/11.png)
- Bước này cũng Next
  ![Hiển thị](./b2p1images/12.png)
- Bước này chọn Active Directory Domain Services
  ![Hiển thị](./b2p1images/13.png)
  - Cửa sổ Add Roles and Features Wizard hiện ra, chọn Add Features.
  ![Hiển thị](./b2p1images/14.png)
- Rồi nhấn Next nhé
  ![Hiển thị](./b2p1images/15.png)
  - Bước này nhấn Next tiếp nhé
  ![Hiển thị](./b2p1images/16.png)
  - Next tiếp
  ![Hiển thị](./b2p1images/17.png)
  - bước này tích chọn vào restart the destination server automatically is required .Rồi ấn install
  ![Hiển thị](./b2p1images/18.png)
  - KHI cài xong các bạn nhấn đóng là được
  ![Hiển thị](./b2p1images/19.png)
  - Để làm tiếp bước này các bạn cần đặt mật khẩu cho Administrator trên máy server1.Để tránh cài đặt bị lỗi nhé
  ![Hiển thị](./b2p1images/20.png)
  - Đặt mật khẩu cho Administrator .Đầu tiên các bạn nhấn Ctrl + Alt + Delete để vào màn hình login. Nó sẽ hiện ra máy chính trước các bạn chọn "Switch User" cứ nhập mật khẩu máy chính như bình thường rồi vào máy ảo cũng chọn "Switch User" nhé.
  ![Hiển thị](./b2p1images/21.png)
 - Sau đó các bạn nhấn Ctrl + Alt + insert để vào màn hình login.Và các bạn đổi sang User Administrator nhé.Rồi các bạn ấn sign in vào nhé.
  ![Hiển thị](./b2p1images/22.png)
- NÓ yêu cầu thay đổi mật khẩu bạn cứ nhấn oke nhé
  ![Hiển thị](./b2p1images/23.png)
- Các bạn nhập mật khẩu và xác nhận mật khẩu nhé như hình mình làm rồi nhấn nút mũi tên là được
  ![Hiển thị](./b2p1images/24.png)
- Nó hiện như này nhấn "ok"
  ![Hiển thị](./b2p1images/25.png)
  - Rồi các bạn nhấn sign in vào nhé
  ![Hiển thị](./b2p1images/26.png)
- Rồi nó sẽ vào màn hình như này trên thanh công cụ server manager nhấn vào biểu tượng của hình tam giác cảnh báo chọn promote this server to a domain controller
  ![Hiển thị](./b2p1images/27.png)
  - ở bước này các bạn tích chọn vào "Add a new forest" rồi đặt tên miền mới như trong hình theo yêu cầu của thầy nhé sau đó nhấn "Next"
  ![Hiển thị](./b2p1images/28.png)
  - ở bước này cac bạn nhập mật khẩu cho domain controller nhé. Mình để là 123456a@.Rồi nhấn "next"
  ![Hiển thị](./b2p1images/29.png)
  - Bước này cứ next nhé
  ![Hiển thị](./b2p1images/30.png)
  - Bước này cũng next nhé
  ![Hiển thị](./b2p1images/31.png)
  - Next tiếp
  ![Hiển thị](./b2p1images/32.png)
  - NExt tiếp
  ![Hiển thị](./b2p1images/33.png)
  - Đến Bước này như này mới là oke nhé xong các bạn nhấn install là được xong máy sẽ khởi động lại khi cài xong .
  ![Hiển thị](./b2p1images/34.png)
  **_Chú ý_:** Bạn nào bị lỗi mà không nhấn install được là chưa cài pass cho Administrator nhé. Mình có hướng dẫn cài ở trên rồi nhé
- Nhấn close để khởi động lại máy
  ![Hiển thị](./b2p1images/35.png)
- Các bạn đăng nhập lại vào máy với tài khoản Administrator và mật khẩu vừa tạo nhé.Nhẫn ctrl + alt + insert để vào màn hình login.
  ![Hiển thị](./b2p1images/36.png)
  - bạn kiểm tra xem nó đã có domain chưa bằng cách vào "Cài đặt" -> chọn " System" -> chọn "About" -> chọn"system infor"
  ![Hiển thị](./b2p1images/37.png)
  - chỗ mình đặt chuột là thành công rồi nhé
  ![Hiển thị](./b2p1images/38.png)
  - Rồi các bạn vào sửa lại card mạng như này nhé
  ![Hiển thị](./b2p1images/39.png)
### Join Domain
- Bạn vào máy win10 ping lại 1 lần nữa xem có được không nhé rồi mới thực hiện join domain nhé.
- Ping thành công các bạn join domain như sau :
  - Các bạn cũng vào setting chọn "System" -> chọn "About" -> chọn "Rename this Pc(advanced)"
  ![Hiển thị](./b2p1images/40.png)
  - Tiếp theo bạn nhấn "change"
  ![Hiển thị](./b2p1images/41.png)
  - Rồi các bạn tích vào ô Domain và nhập tên domain như trong hình rồi nhấn "ok"
  ![Hiển thị](./b2p1images/42.png)
  - NÓ yêu cầu nhập mật khẩu để join domain bạn làm như hình là được
  ![Hiển thị](./b2p1images/43.png)
  - HIển thị như này là được nhé nó nhẫn ok và đóng tất cả các cái vừa mở rồi nhấn restartnow là ok
  ![Hiển thị](./b2p1images/44.png)
