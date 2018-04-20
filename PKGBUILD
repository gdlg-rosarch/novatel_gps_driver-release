# Script generated with Bloom
pkgdesc="ROS - Driver for NovAtel receivers"


pkgname='ros-kinetic-novatel-gps-driver'
pkgver='3.4.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('boost'
'libpcap'
'ros-kinetic-catkin'
'ros-kinetic-diagnostic-msgs'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-gps-common'
'ros-kinetic-nav-msgs'
'ros-kinetic-nodelet'
'ros-kinetic-novatel-gps-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-swri-math-util'
'ros-kinetic-swri-nodelet'
'ros-kinetic-swri-roscpp'
'ros-kinetic-swri-serial-util'
'ros-kinetic-swri-string-util'
'ros-kinetic-tf'
)

depends=('boost'
'libpcap'
'ros-kinetic-diagnostic-msgs'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-gps-common'
'ros-kinetic-nav-msgs'
'ros-kinetic-nodelet'
'ros-kinetic-novatel-gps-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-swri-math-util'
'ros-kinetic-swri-nodelet'
'ros-kinetic-swri-roscpp'
'ros-kinetic-swri-serial-util'
'ros-kinetic-swri-string-util'
'ros-kinetic-tf'
)

conflicts=()
replaces=()

_dir=novatel_gps_driver
source=()
md5sums=()

prepare() {
    cp -R $startdir/novatel_gps_driver $srcdir/novatel_gps_driver
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
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

