#Gentoo
<pre>



ciclo /usr/src # cp linux-4.9.76-gentoo-r1/.config linux-4.9.95-gentoo/
ciclo /usr/src/linux-4.9.95-gentoo # make && make modules_install && make install && mount /boot && boot-update 

<hr />

Backup grub.cfg prior to running the follwing script:
White grub2 and efi (uefi)  run #grub2-mkconfig -o /boot/grub/grub.cfg  to set grub boot
#notes 170111 : grub-mkconfig -o /boot/grub/grub.cfg  to set grub boot
Add the following to  /boot/grub/grub.cfg

linux   /vmlinuz-4.4.6-gentoo root=/dev/sda4 ro root=/dev/sda4 ro init=/usr/lib/systemd/systemd
around line 107

//notes from 180204 line 107 /////////////////////////////////////////////////////////////////////////
linux   /vmlinuz-4.9.76-gentoo-r1 root=/dev/sda4 ro init=/usr/lib/systemd/systemd
/////////////////////////////////////////////////////////////////////////////////////////////////////

cp /usr/src/linux-2.6.34-gentoo-r12/arch/x86_64/boot/bzImage /boot/kernel-2.6.34-gentoo-r1

link source
ln -s /usr/src/linux-3.12.21-gentoo-r1 /usr/src/linux


170204
added ro init=/usr/lib/systemd/systemd 
to /boot/grub/grub.cfg 

line 107: 
linux /vmlinuz-4.4.39-gentoo root=/dev/sda4 ro root=/dev/sda4 ro init=/usr/lib/systemd/systemd


170806
grub2-mkconfig -o /boot/grub/grub.cfg 

180527
cd /boot/grub
/boot/grub #/ nano grub.cfg -c
added the following
linux   /vmlinuz-4.9.95-gentoo root=/dev/sda4 ro   root=/dev/sda4 ro init=/usr/lib/systemd/systemd

 # eselect kernel list
Available kernel symlink targets:
  [1]   linux-4.9.76-gentoo-r1
  [2]   linux-4.9.95-gentoo *

</pre>
