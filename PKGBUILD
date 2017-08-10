pkgname='pijul'
pkgver='0.7.2'
pkgrel=1
pkgdesc='A distributed version control system based on a sound theory of patches.'
url='https://pijul.org'
makedepends=('cargo' 'pijul') # Baron Munchausen!
arch=('i686' 'x86_64')
license=('GPL')
source=()
sha256sums=()

prepare ()
{
    cd "$srcdir"
    pijul clone 'https://nest.pijul.com/pijul_org/pijul'
}

pkgver ()
{
    cd "$srcdir"/'pijul'
    cd 'pijul'
    cat Cargo.toml |
        grep '^version = ' |
            sed 's/version[ ]*=[ ]"\(.*\)"/\1/'
}

build ()
{
    cd "$srcdir"/'pijul'
    (cd pijul && cargo build --release)
    [ $? -eq 0 ] || exit $?
}

package ()
{
    cd "$srcdir"/'pijul'
    cd 'pijul'
    install -D 'target/release/pijul' "$pkgdir"/usr/bin/'pijul'
}
