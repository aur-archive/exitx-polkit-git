
pkgname=exitx-polkit-git
pkgver=20110301
pkgrel=1
pkgdesc="GTK logout dialog for Openbox with PolicyKit support"
arch=('i686' 'x86_64')
url="http://www.linuxsir.com/bbs/lastpostinthread350740.html"
license=('GPL2')
depends=('gtk2' 'gettext' 'pm-utils')
conflicts=('exitx-systemd-git')

_gitroot=https://github.com/z0id/exitx-polkit
_gitname=exitx-polkit

build() {
	cd "$srcdir"
	msg "Connecting to GIT server...."
	
	if [ -d ${_gitname} ] ; then
		cd ${_gitname} && git pull origin
		msg "The local files are updated."
	else
		git clone ${_gitroot} ${_gitname}
	fi
	
	msg "GIT checkout done or server timeout"

    	cd $srcdir/$_gitname
	make

 
}
package() {
    install -Dm755 ${srcdir}/${_gitname}/exitx  ${pkgdir}/usr/bin/exitx
	}
