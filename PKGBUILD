# Maintainer: BanHammer



pkgname=mts-link
pkgver=1.2.13
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
sha256sums=("4e411c12bf4656a8a873bdfee6a50b1a98cb9619d337f5b09d49e399cbbf570a")

prepare() {
    tar -xf data.tar.xz
    mv "${srcdir}""/opt/MTS Link Meetings" "${srcdir}"/opt/mts-link
    mv "${srcdir}""/opt/mts-link/mts-link-meetings" "${srcdir}"/opt/mts-link/mts-link
    rm -rf "${srcdir}""/opt/mts-link/MTS Link"
    sed -i 's|/opt/MTS Link/mts-link|/opt/mts-link/mts-link|g' "${srcdir}"/usr/share/applications/mts-link-meetings.desktop
}

package() {
    cp -dr --no-preserve=ownership opt usr "${pkgdir}"/
    install -D -m0644 "${pkgdir}"/usr/share/icons/hicolor/0x0/apps/mts-link-meetings.png "${pkgdir}"/usr/share/pixmaps/${pkgname}.png
    chmod 755 "${pkgdir}""/opt/${pkgname}/mts-link"
}
