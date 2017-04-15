# FreeBSD support

## status

- works:
  - compiles
  - starts
  - successfully indexes .desktop-files
- fails:
  - plot twist: does not show any application on input in main app
  - some FileSystemWatchers fail, because the given addPath is empty
  - coredumps, coredumps, coredumps

## installation

pkg install cmake qt5
cd /usr/ports/math/muparser
make install

git clone https://github.com/bebehei/albert.git
git -C albert checkout freebsd-support
cmake albert
make -j$(nproc)
make install
