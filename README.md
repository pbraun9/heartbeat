# The golden age of Linux-HA

Debian & Ubuntu are maintaining a patchset for the good old heartbeat package.  This is an attempt to keep-up with it [for Slackware Linux](https://pub.nethence.com/daemons/linuxha-oldschool).

for the record, here's how this repo gets generated and updated.

	git clone https://github.com/pbraun9/heartbeat.git
	cd heartbeat/
	rm -rf * # only .git/ remains

grab the latest patchset from ubuntu or debian package repositories

        wget http://deb.debian.org/debian/pool/main/h/heartbeat/heartbeat_3.0.6-11.debian.tar.xz
        tar xaf heartbeat_3.0.6-11.debian.tar.xz

grab the now unmaintained source from linux-ha (it's still up)

        hg clone http://hg.linux-ha.org/dev heartbeat-dev
	mv heartbeat-dev/* ./
	rm -rf heartbeat-dev/

apply all debian patches (there are a few hunks since we're not exactly targeting the .orig file)

        ls -lF debian/patches/
        for patch in debian/patches/*.patch; do
                echo PATCH $patch
                patch -p1 < $patch
                echo
        done; unset patch
	rm -rf debian/

update this GIT repo accordingly

	git status
	git commit -a
	git push

	git tag 3.0.6-10
	git push --tags

## Resources

3.2. Building and installing Heartbeat from source
http://www.linux-ha.org/doc/users-guide/_building_and_installing_heartbeat_from_source.html

Heartbeat 3.0 / summary
http://hg.linux-ha.org/heartbeat-STABLE_3_0/summary

### debian package

Package: heartbeat (1:3.0.6-11)
https://packages.debian.org/unstable/heartbeat

Package: heartbeat (1:3.0.6-11)
https://packages.debian.org/testing/heartbeat

Package: heartbeat (1:3.0.6-9)
https://packages.debian.org/stable/heartbeat

### ubuntu package

Package: heartbeat (1:3.0.6-10build1) [universe]
https://packages.ubuntu.com/focal/heartbeat

heartbeat 1:3.0.6-10 source package in Ubuntu
https://launchpad.net/ubuntu/+source/heartbeat/1:3.0.6-10

Source Package: heartbeat (1:3.0.6-10build1) [universe]
https://packages.ubuntu.com/source/focal/heartbeat

