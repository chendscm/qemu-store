BASEDIR := $(shell pwd)

create: 
	qemu-img create -f qcow2 win11.qcow2 200G

install:
	qemu-system-x86_64 \
	-cdrom /home/chend/Sync/iso/zh-cn_windows_11_business_editions_version_22h2_updated_feb_2023_x64_dvd_632649a2.iso \
	-boot order=d \
	-accel kvm \
	-smp 4 \
	-m 8G \
	-machine usb=on -device usb-tablet \
	-drive file=/home/chend/git/qemu-store/mb16s/win11/win11.qcow2,format=qcow2

run:
	qemu-system-x86_64 \
	-accel kvm \
	-smp 4  \
	-m 8G \
	-vga qxl -device qxl \
	-machine usb=on -device usb-tablet \
	-audiodev pa,id=snd0 \
	-net nic -net user \
	-device ich9-intel-hda \
	-device hda-output,audiodev=snd0 \
	-nic user,hostfwd=tcp::10022-:22 \
	/home/chend/git/qemu-store/mb16s/win11/win11.qcow2

.PHONY: create install run
