# Maintainer: Ivan Pulido <ijpulidos[AT]riseup.net>
_gemname=ctioga2
pkgname=ruby-$_gemname
pkgver=0.4
pkgrel=1
pkgdesc="Ruby library for creating high quality figures and plots."
arch=(any)
url="http://tioga.rubyforge.org/index.html"
license=('GPL')
depends=(ruby ruby-tioga texlive-bin) # Full dependency information is available in the yaml specification
makedepends=(rubygems)
source=(http://gems.rubyforge.org/gems/$_gemname-$pkgver.gem)
noextract=($_gemname-$pkgver.gem)
md5sums=('9034894c61a553c6e8394125dce72eee')

package() {
  cd "$srcdir"
  # _gemdir is defined inside package() because if ruby[gems] is not installed on
  # the system, makepkg will exit with an error when sourcing the PKGBUILD.
  local _gemdir="$(ruby -rubygems -e'puts Gem.default_dir')"

  gem install --no-user-install --ignore-dependencies -i "$pkgdir$_gemdir" -n "$pkgdir/usr/bin" \
    "$_gemname-$pkgver.gem"
}

# vim:set ts=2 sw=2 et:
