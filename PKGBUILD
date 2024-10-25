# Maintainer: BanHammer



pkgname=mts-link
pkgver=1.2.6
pkgrel=1
#epoch=1

pkgdesc="Services for business communications and collaboration. Meetings, webinars, corporate messenger, online whiteboards and training courses in one ecosystem."
arch=("x86_64")
license=("custom:mts-link")
categories=("social-networking")

options=(!strip)
url=https://mts-link.ru/

depends=()
optdepends=()

provides=(mts-link)
conflicts=(mts-link)

source=("${pkgname}-${pkgver}.deb::https://apps.webinar.ru/desktop/latest/mts-link-desktop.deb")
sha256sums=("e3284c0d3e97c224290d2579fe94c42ae46b53faf1155decbf0d7efbd8552020")

prepare() {
    tar -xf data.tar.xz
    mv "${srcdir}""/opt/MTS Link" "${srcdir}"/opt/mts-link
    rm -rf "${srcdir}""/opt/mts-link/MTS Link"
    sed -i 's|/opt/MTS Link/mts-link|/opt/mts-link/mts-link|g' "${srcdir}"/usr/share/applications/mts-link.desktop
}

package() {
    cp -dr --no-preserve=ownership opt usr "${pkgdir}"/
    install -D -m0644 "${pkgdir}"/usr/share/icons/hicolor/0x0/apps/mts-link.png "${pkgdir}"/usr/share/pixmaps/${pkgname}.png
    chmod 755 "${pkgdir}""/opt/${pkgname}/mts-link"
}
