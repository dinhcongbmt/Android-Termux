# Android-Termux-Linux-Desktop

#[Lệnh]
#Cách cài đặt Linux Distro trên Termux bằng proot-distro (Không cần Root)
#Các bước được thực hiện như sau.
#Mở Termux
#Cài đặt proot-distro

pkg update

pkg install x11-repo

pkg install termux-x11-nightly

pkg install proot-distro

pkg install pulseaudio

Pkg install bash

pkg install wget

pkg install git

git clone https://github.com/termux/proot-distro

cd proot-distro ./install.sh

#Cài đặt Debian (hoặc distro bạn thích)

proot-distro install debian

#Login vào Debian bằng ueser root

proot-distro login debian

#Tạo người dùng có quyền sudo và cài GNU nano

apt update -y

apt install sudo nano adduser -y

#Tạo người dùng và mật khẩu (thay user name bằng tên người dùng của bạn đặt).

adduser username

#Cấp cho người dùng quyền sudo.

nano /etc/sudoers

#Trong GNU nano xóa $sudo và thêm dòng bên dưới vào file,^ là phím ctrl,M là phím Alt, sửa xong bấm ctrl X để exit, hỏi lưu không thì bấm Y rồi bấm Enter.

username ALL=(ALL:ALL) ALL

#login vào username kiểm tra xem bạn có thể thực hiện lệnh sudo không bằng lệnh bên dưới (nó sẽ trả về root).

sudo whoami

# Cài đặt Desktop UI Gnome
#Login vào Debian bằng user của bạn.

proot-distro login debian --user username

#chạy lệnh sau để cài Gnome

sudo apt install dbus-x11 nano gnome gnome-shell gnome-terminal gnome-tweaks gnome-software nautilus gnome-shell-extension-manager gedit tigervnc-tools gnupg2 -y

#Cài xong tiếp tục chạy lệnh bên dưới.

for file in $(find /usr -type f -iname "*login1*"); do rm -rf $file done

# Chạy Desktops để sử dụng với Termux X11
#Ghi chú

Theo mặc định, tập lệnh này hoạt động với người dùng "dinhcongbmt". Nếu bạn tạo usename có tên khác trong proot-distro, vui lòng thay đổi nơi ghi "dinhcongbmt" bên trong tập lệnh.
#Tải xuống tập lệnh bên dưới, cấp quyền thực thi và chạy tập lệnh đó (trong Termux, không phải trong proot-distro):

#Cài Tập lệnh Startgnome_debian.sh với lệnh wget.

wget https://raw.githubusercontent.com/dinhcongbmt/Android-Termux/refs/heads/main/startgnome_debian.sh

#Chạy lệnh bên dưới để vào GUI Desktop

chmod +x startgnome_debian.sh

#Sau đó chạy lênh dưới đậy.

./startgnome_debian.sh











