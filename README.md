# hyprtoolkit-debian
Mirror of https://salsa.debian.org/hyprland-team/hyprtoolkit

Used for hyprplus (since PikaOS does not package this anymore)

## Build
`gbp buildpackage -us -uc --git-ignore-new` inside cloned directory.

## Install
`sudo dpkg -i *.deb` inside cloned folder after building.
