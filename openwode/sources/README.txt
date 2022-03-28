This directory contains the git bundle with the full OpenWode repository. This incldues everything needed to generate your own OpenWode uImage files.

To extract this, use the following commands:
	mkdir openwode
	cd openwode
	git init
	git pull <path-to-git-bundle>
	git fetch --tags <path-to-git-bundle>

To build the resulting source tree, use:
	./build.sh prepare
	./build.sh build

The prepare step is only required once, next time you build you can directly do "./build.sh build". The script
captures all build output in a file called compile.log for review in case of problems.

The source tree (and prebuilt image) contains a demo package called 'testapp', which is an example of how to
add a package to the tree, and shows how to use the display and joystick on the WODE.

For details on git, see: http://git-scm.com/
For details on building OpenWRT, see: http://wiki.openwrt.org/doc/howto/build
For details on adding packages to OpenWRT: http://wiki.openwrt.org/doc/devel/packages
