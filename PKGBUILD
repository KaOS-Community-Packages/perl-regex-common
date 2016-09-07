pkgname=perl-regex-common
_dist=Regexp--Common
pkgver=2016060801
pkgrel=1
pkgdesc='Regexp::Common - Provide commonly requested regular expressions'
arch=('x86_64')
depends=('perl>=5.10')
url='https://github.com/Abigail/Regexp--Common'
license=('PerlArtistic' 'PerlArtistic-2.0' 'BSD' 'MIT')
options=('!emptydirs' 'purge')
source=("${url}/archive/release-${pkgver}.tar.gz")
md5sums=('27644c4cdd12d214f335617b81b28667')

build() {
  cd "${srcdir}/${_dist}-release-${pkgver}"
  unset PERL5LIB PERL_MM_OPT PERL_LOCAL_LIB_ROOT
  export PERL_MM_USE_DEFAULT=1 PERL_AUTOINSTALL=--skipdeps
  /usr/bin/perl Makefile.PL
  make
}


check() {
  cd "${srcdir}/${_dist}-release-${pkgver}"
  unset PERL5LIB PERL_MM_OPT PERL_LOCAL_LIB_ROOT
  export PERL_MM_USE_DEFAULT=1
  make test
}


package() {
  cd "${srcdir}/${_dist}-release-${pkgver}"
  unset PERL5LIB PERL_MM_OPT PERL_LOCAL_LIB_ROOT
  make install INSTALLDIRS=vendor DESTDIR="${pkgdir}"
}

