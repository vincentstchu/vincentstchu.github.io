近期碰到的问题1:
archlinux下android studio的AVD打不开的方法：
Fix libGL error: unable to load driver: i965_dri.so

I have Android Studio 2.1.1 and updated mesa driver (11.2.1-1 -> 11.2.2-1).

This morning I got following error: libGL error: unable to load driver: i965_dri.so.

Solution

# Arch Linux
mv ~/Android/Sdk/tools/lib64/libstdc++/libstdc++.so.6{,.bak}
mv ~/Android/Sdk/tools/lib64/libstdc++/libstdc++.so.6.0.18{,.bak}
ln -s /usr/lib/libstdc++.so  ~/Android/Sdk/tools/lib64/libstdc++/

近期碰到的问题2:
开关机啪啪响解决方法：
	在/etc/modprobe.d/下创建文件modprobe.conf并添加代码：options snd-hda-intel model=,generic

耳机电流声解决：
	sudo alsamixer
按F6选择第二个（HDA INTEL PCH），然后把auto mute改为disable
	sudo alsactl store

