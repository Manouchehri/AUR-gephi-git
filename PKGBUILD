# Maintainer: David Manouchehri <manouchehri@riseup.net>
# Contributor: Morten Linderud <morten@linderud.pw>
# Contributor: Andreas Krinke <andreas dot krinke at gmx dot de>

_gitname=gephi
pkgname="${_gitname}-git"
_gitbranch=master
_gitauthor=gephi
pkgver=r3812.d17eb89
pkgrel=1
pkgdesc="An interactive graph visualization and exploration platform"
url="https://gephi.github.io/"
license=('CDDL' 'GPL3')
source=("git://github.com/${_gitauthor}/${_gitname}#branch=${_gitbranch}")
sha512sums=('SKIP')
arch=('armv6h' 'armv7h' 'i686' 'x86_64')
depends=('java-runtime' 'libxxf86vm' 'jdk7-openjdk')
makedepends=('git' 'maven')
conflicts=("${_gitname}")
provides=("${_gitname}")

pkgver() {
  cd "${srcdir}/${_gitname}"
  (
    set -o pipefail
    git describe --long 2>/dev/null | sed 's/\([^-]*-g\)/r\1/;s/-/./g' ||
      printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
  )
}

build() {
  cd "${srcdir}/${_gitname}"
  mvn clean install
}

package() {
  cd "${srcdir}/${_gitname}"
  exit 1
}

# vim:set et sw=2 sts=2 tw=80: