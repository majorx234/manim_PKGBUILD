# Contributor: Sholum <wallyssonryu@gmail.com>
# Maintainer: Stefan Husmann <stefan-husmann@t-online.de>

pkgname='manim'
pkgver=0.17.1
pkgrel=1
pkgdesc="Animation engine for explanatory math videos"
arch=('any')
url="https://github.com/ManimCommunity/manim"
license=('MIT' 'custom:3Blue1Brown LLC')
depends=('cairo' 
         'ffmpeg' 
         'sox'
	 'python-argparse'
	 'python-colour'
	 'python-numpy'
	 'python-pillow'
	 'python-progressbar'
	 'python-scipy'
	 'python-tqdm'
#opencv-python==3.4.2.17
	 'python-cairocffi'
	 'python-pydub'
	 'python-pbr'
         'python-poetry'
	)
makedepends=(git python-build python-installer python-wheel)
optdepends=('texlive-bin: latex support'
            'texlive-core: latex support'
            'texlive-latexextra: latex support'
            'texlive-bibtexextra: latex support'
            'tllocalmgr-git: latex support')
source=("$pkgname-$pkgver.tar.gz::$url/archive/v$pkgver.tar.gz")
sha256sums=('30c10c92f314e74c1d1acd438c8146be72308d36874b72107870be5a853edffc')

build() {
  cd "${pkgname}-$pkgver"
  python -m build --wheel --no-isolation
}

package() {
  cd "${pkgname}-$pkgver"
	
  install -Dm644 README.md "${pkgdir}/usr/share/doc/${pkgname}/README.md"
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  python -m installer --destdir="$pkgdir" dist/*.whl
}
