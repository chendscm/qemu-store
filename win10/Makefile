BASEDIR := $(shell pwd)

create: 
	qemu-img create -f qcow2 win10.qcow2 150G

install:
	qemu-system-x86_64 \
	-cdrom /home/user/data/iso/cn_windows_10_business_editions_version_1909_updated_jan_2020_x64_dvd_b3e1f3a6.iso \
	-boot order=d \
	-accel kvm \
	-smp 4 \
	-m 8G \
	-machine usb=on -device usb-tablet \
	-drive file=/home/user/git/qemu-script/win10/win10.qcow2,format=qcow2

run:
	qemu-system-x86_64 \
	-accel kvm \
	-smp 4  \
	-m 8G \
	-vga qxl \
	-machine usb=on -device usb-tablet \
	/home/user/git/qemu-script/win10/win10.qcow2

.PHONY: create install run
