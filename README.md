# Android-Termux-Linux-Desktop

#[Lệnh]
#Cách cài đặt Linux Distro trên Termux #bằng proot-distro (Không cần Root)
#Các bước được viết như sau:
#Mở Termux
#Cài đặt proot-distro

pkg update

pkg install x11-repo

pkg install termux-x11-nightly

pkg install proot-distro

pkg install pulseaudio

Pkg install bash

Pkg install git

git clone https://github.com/termux/proot-distro

cd proot-distro ./install.sh

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

adduser username

#Cấp cho người dùng quyền sudo

usermod -aG sudo username

#Thêm dòng bên dưới vào file .sh

username ALL=(ALL:ALL) ALL

#Kiểm tra xem bạn có thể thực hiện lệnh sudo không (nó sẽ trả về sudo:x:27:username )

getent group sudo

# Cài đặt Desktop
#Desktop UI Gnome 

proot-distro login debian --user <username của bạn>

sudo apt install dbus-x11 nano gnome gnome-shell gnome-terminal gnome-tweaks gnome-software nautilus gnome-shell-extension-manager gedit tigervnc-tools gnupg2 -y

for file in $(find /usr -type f -iname "*login1*"); do rm -rf $file
done

# Chạy Desktops để sử dụng với Termux X11
#Tất cả các tập lệnh trong kho lưu trữ này đều được chuẩn bị để chạy nhiều máy tính để bàn khác nhau có âm thanh một cách dễ dàng.
#Đầu tiên bạn cần cài đặt các gói sau vào Termux:

pkg update

pkg install x11-repo

pkg install termux-x11-nightly

pkg install pulseaudio

Sau đó, bạn chỉ cần tải xuống tập lệnh tương ứng với Desktop bạn đã cài đặt, cấp quyền thực thi và chạy tập lệnh đó (trong Termux, không phải trong proot-distro):

# Download the script to Termux

chmod +x startgnome_debian.sh
./startgnome_debian.sh


Ghi chú

Theo mặc định, tập lệnh này hoạt động với người dùng "droidmaster". Nếu bạn tạo người dùng có tên khác trong proot-distro, vui lòng thay đổi nơi ghi "dinhcongbmt" bên trong tập lệnh.

bắt đầu gnome_debian.sh

wget https://raw.githubusercontent.com/LinuxDroidMaster/Termux-Desktops/main/scripts/proot_debian/startgnome_debian.sh







