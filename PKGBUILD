pkgname=astromenace
pkgver=1.3.2
pkgrel=1
pkgdesc='Hardcore 3D space shooter with spaceship upgrade possibilities.'
arch=('x86_64')
url='http://www.viewizard.com/'
license=('GPL3')
source=("http://sourceforge.net/projects/openastromenace/files/${pkgver}/${pkgname}-src-${pkgver}.tar.bz2"
        "${pkgname}.desktop")
depends=("sdl" "openal" "libogg" "libvorbis" "freetype2" "glu" "freealut")
md5sums=('a1481ca7cf498773fddc16a3b41c9b9b'
         'a993bd947fc349015ff1daedb72e4e9b')

build() {
    cd AstroMenace
    cmake ./
    make
    ./AstroMenace --pack --rawdata=./RAW_VFS_DATA
}


package() {
    install -Dm755 $srcdir/AstroMenace/AstroMenace $pkgdir/usr/bin/$pkgname
    install -Dm644 $srcdir/AstroMenace/gamedata.vfs $pkgdir/usr/share/$pkgname/gamedata.vfs
    install -Dm644 $srcdir/AstroMenace/astromenace_128.png $pkgdir/usr/share/pixmaps/$pkgname.png
    install -Dm644 $srcdir/$pkgname.desktop $pkgdir/usr/share/applications/$pkgname.desktop
}

