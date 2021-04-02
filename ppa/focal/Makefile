all: Packages.gz Release.gpg InRelease

Packages: *.deb
	dpkg-scanpackages --multiversion . > Packages
Packages.gz: Packages
	gzip -k -f Packages
Release: *.deb
	apt-ftparchive release . > Release
Release.gpg: Release
	gpg --default-key admin+ppa@geneanet.org -abs -o - Release > Release.gpg
InRelease: Release
	gpg --default-key admin+ppa@geneanet.org --clearsign -o - Release > InRelease
