SUBDIRS = src po

PWD=$(shell pwd)

ipkg: enigma2-plugin-systemplugins-wirelesslan.ipk

enigma2-plugin-systemplugins-wirelesslan.ipk:
	make install DESTDIR=${PWD}/ipkg/INSTALL
	tar czf ipkg/data.tar.gz -C ipkg/INSTALL/ .
	echo 2.0 > ipkg/debian-binary
	tar czf ipkg/control.tar.gz -C CONTROL/ ./control
	rm -f $@
	ar q $@ ipkg/control.tar.gz ipkg/debian-binary ipkg/data.tar.gz
	rm -rf ipkg/