# Maintainer: Rafik El Hadi Houari <rehhouari@gmail.com>

pkgname=nodejs-bunny
pkgver=0.0.1
pkgrel=1
pkgdesc="Barebones shims for using Bun instead of Node.js and npm."
arch=('any')
url="https://github.com/rehhouari/nodejs-bunny"
license=('MIT')
optdepends=('bun')
provides=('nodejs' 'npm' 'yarn' 'pnpm')
conflicts=('nodejs' 'npm' 'yarn' 'pnpm' 'nodejs-lts-gallium'
    'nodejs-lts-hydrogen' 'nodejs-lts-iron')

prepare() {
    cat <<EOF >node-wrapper
#!/bin/sh
exec bun "\$@"
EOF

    cat <<EOF >npm-wrapper
#!/bin/sh
exec bun install "\$@"
EOF

    cat <<EOF >npx-wrapper
#!/bin/sh
exec bun x "\$@"
EOF
}

package() {
    install -Dm755 node-wrapper "$pkgdir/usr/bin/node"
    install -Dm755 npm-wrapper "$pkgdir/usr/bin/npm"
    install -Dm755 npx-wrapper "$pkgdir/usr/bin/npx"

    # Symlink others directly to bun
    ln -s /usr/bin/bun "$pkgdir/usr/bin/yarn"
    ln -s /usr/bin/bun "$pkgdir/usr/bin/pnpm"
}
