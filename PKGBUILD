# Generated by Xyne::Arch::CPAN 0.07

pkgname=perl-barcode-code128
pkgver=2.01
pkgrel=1
pkgdesc="Generate CODE 128 bar codes"
arch=('i686' 'x86_64')
url="http://search.cpan.org/dist/Barcode-Code128/"
license=('unknown')
source=('http://search.cpan.org/CPAN/authors/id/W/WR/WRW/Barcode-Code128-2.01.tar.gz')
md5sums=('a0aa077b26926c30659471d14515d907')
sha256sums=('6528167a5ecd34e6b4724b891db6c9dcecf3c7de654acaf76e9f42c09d4352c2')
depends=('perl')
options=(!emptydirs)

build() {
  _dir=$(find $srcdir -maxdepth 2 -type f -name 'Makefile.PL')
  if [ ! -z "$_dir" ]; then
    cd $(dirname "$_dir")
    PERL_MM_USE_DEFAULT=1 perl Makefile.PL INSTALLDIRS=vendor || return 1
    make  || return 1
    make install DESTDIR="${pkgdir}" || return 1

  else
  _dir=$(find $srcdir -maxdepth 2 -type f -name 'Build.PL')
  if [ ! -z "$_dir" ]; then
    cd $(dirname "$_dir")
    PERL_MM_USE_DEFAULT=1 perl Build.PL INSTALLDIRS=vendor || return 1
    ./Build  || return 1
    ./Build install destdir=${pkgdir} || return 1

  else
    echo "error: failed to detect build method for $pkgname"
    echo "you may be able to fix this by editing the PKGBUILD"
    return 1
  fi fi

  # remove perllocal.pod and .packlist
  find ${pkgdir} -name perllocal.pod -delete
  find ${pkgdir} -name .packlist -delete
}

# vim:set ts=2 sw=2 et:

