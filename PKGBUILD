pkgname=evopop-gtk-theme-x11tete11x-mod
_pkgname=evopop-gtk-theme
pkgver=0.28
pkgrel=1
pkgdesc="A simple, flat and bold Gtk theme for Evolve OS & Budgie Desktop. Iris Dark was used as base. Modded by x11tete11x"
arch=('any')
url="https://github.com/solus-project/evopop-gtk-theme"
license=('GPL3')
depends=('gtk3>=3.16')
provides=('evopop-gtk-theme', 'evopop-light-gtk-theme')
conflicts=('evopop-gtk-theme-x11tete11x-mod')
source=("${_pkgname}-${pkgver}.tar.gz::https://github.com/solus-project/evopop-gtk-theme/archive/$pkgver.tar.gz")
sha256sums=('3ec60b86f0075d19c6cb2b8d5fb704408059708d575e3bc70ebbf2101e340aea')


build() {
  cd $_pkgname-$pkgver

  autoreconf -vfi
  ./configure --prefix=/usr $*
}

package() {
  cd $_pkgname-$pkgver

  make DESTDIR=${pkgdir} install
  #x11tete11x mod
  mv ${pkgdir}/usr/share/themes/evopop-gtk-theme ${pkgdir}/usr/share/themes/evopop-gtk-theme-x11tete11x-mod
  mv ${pkgdir}/usr/share/themes/evopop-light-gtk-theme ${pkgdir}/usr/share/themes/evopop-light-gtk-theme-x11tete11x-mod
  #MOD
  cd ${pkgdir}/usr/share/themes/evopop-gtk-theme-x11tete11x-mod/gtk-3.0
  sed -i 's/#31363d/#2D2D2D/I' gtk.css
  sed -i 's/#31363d/#2D2D2D/I' gtk-dark.css
  sed -i 's/#505359/#2D2D2D/I' gtk-dark.css
  cd ${pkgdir}/usr/share/themes/evopop-gtk-theme-x11tete11x-mod/
  sed -i 's/EvoPop/EvoPop-x11tete11x-mod/I' index.theme
  cd ${pkgdir}/usr/share/themes/evopop-gtk-theme-x11tete11x-mod/gtk-2.0
  sed -i 's/#31363d/#2D2D2D/I' gtkrc
}
