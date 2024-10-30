# Android-Termux-Linux-Desktop

#[Lệnh]
#Cách cài đặt Linux Distro trên Termux #bằng proot-distro (Không cần Root)
#Các bước được viết như sau:
#Mở Termux
#Cài đặt proot-distro

pkg update

pkg install proot-distro

#Cài đặt Debian (hoặc distro bạn thích)

proot-distro install debian

#Đăng nhập vào bản phân phối

proot-distro login debian

#[Lệnh]
#Tạo người dùng có quyền sudo
#Các bước thực hiện như sau.
#Cài đặt các gói cần thiết

apt update -y
apt install sudo nano adduser -y

#Tạo người dùng

adduser <username của bạn>

#Cấp cho người dùng quyền sudo
nano /etc/sudoers

#Thêm dòng bên dưới vào file .sh
 <username của bạn> ALL=(ALL:ALL) ALL

#Kiểm tra xem bạn có thể thực hiện #lệnh sudo không (nó sẽ trả về root)

sudo whoami 






