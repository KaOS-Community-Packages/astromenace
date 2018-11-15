pkgname=astromenace
pkgver=1.4.0
pkgrel=1
pkgdesc='Hardcore 3D space shooter with spaceship upgrade possibilities.'
arch=('x86_64')
url='http://www.viewizard.com/'
license=('GPL3')
source=("https://github.com/viewizard/${pkgname}/archive/v${pkgver}.tar.gz"
        "${pkgname}.desktop")
depends=("sdl" "openal" "libogg" "libvorbis" "freetype2" "glu" "freealut")
md5sums=('150e5d2aa6610c7ea23216edbcd03b6e'
         'a993bd947fc349015ff1daedb72e4e9b')

build() {
    cd $pkgname-$pkgver
    cmake ./
    make
}

package() {
    install -Dm755 $srcdir/$pkgname-$pkgver/$pkgname $pkgdir/usr/bin/$pkgname
    install -Dm644 $srcdir/$pkgname-$pkgver/gamedata.vfs $pkgdir/usr/share/$pkgname/gamedata.vfs
    install -Dm644 $srcdir/$pkgname-$pkgver/share/astromenace_128.png $pkgdir/usr/share/pixmaps/$pkgname.png
    install -Dm644 $srcdir/$pkgname.desktop $pkgdir/usr/share/applications/$pkgname.desktop
}
