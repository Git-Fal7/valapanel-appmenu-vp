pkgname="valapanel-appmenu-xfce"
pkgver=0.7.4
pkgrel=1
pkgdesc="appmenu for xfce"
arch=(any)
_opts=(
	--prefix=/usr
	--libdir=lib
	--libexecdir=lib
	-Dauto_features=disabled
  -Dxfce=enabled
)
depends=('gtk3' 'bamf>=0.5.0' 'xfce4-panel>=4.11.2' 'libwnck3' 'vala' 'meson')
optdepends=('gtk2-ubuntu: for hiding gtk2 menus'
            'unity-gtk-module: for gtk2/gtk3 menus'
            'vala-panel-appmenu-registrar: for DBusMenu registrar' 
			'jayatana: for Java applications support'
            'appmenu-qt: for qt4 menus'
            'appmenu-qt5: for qt5 menus')
license=("GPL")
source=('git+https://github.com/git-fal7/valapanel-appmenu-vp')
sha256sums=('SKIP')

package() {
  cd "${srcdir}/valapanel-appmenu-vp"
  meson ./build/ ${_opts[@]}
  cd ./build/
  ninja
  ninja install
}
