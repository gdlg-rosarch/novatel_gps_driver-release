# Script generated with Bloom
pkgdesc="ROS - Messages for proprietary (non-NMEA) sentences from Novatel GPS receivers."


pkgname='ros-lunar-novatel-gps-msgs'
pkgver='3.4.0_1'
pkgrel=1
arch=('any')
license=('Southwest Research Institute Proprietary'
)

makedepends=('ros-lunar-catkin'
'ros-lunar-message-generation'
'ros-lunar-std-msgs'
)

depends=('ros-lunar-message-runtime'
'ros-lunar-std-msgs'
)

conflicts=()
replaces=()

_dir=novatel_gps_msgs
source=()
md5sums=()

prepare() {
    cp -R $startdir/novatel_gps_msgs $srcdir/novatel_gps_msgs
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

