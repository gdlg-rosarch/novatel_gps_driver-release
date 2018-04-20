# Script generated with Bloom
pkgdesc="ROS - Driver for NovAtel receivers"


pkgname='ros-lunar-novatel-gps-driver'
pkgver='3.4.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('boost'
'libpcap'
'ros-lunar-catkin'
'ros-lunar-diagnostic-msgs'
'ros-lunar-diagnostic-updater'
'ros-lunar-gps-common'
'ros-lunar-nav-msgs'
'ros-lunar-nodelet'
'ros-lunar-novatel-gps-msgs'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
'ros-lunar-std-msgs'
'ros-lunar-swri-math-util'
'ros-lunar-swri-nodelet'
'ros-lunar-swri-roscpp'
'ros-lunar-swri-serial-util'
'ros-lunar-swri-string-util'
'ros-lunar-tf'
)

depends=('boost'
'libpcap'
'ros-lunar-diagnostic-msgs'
'ros-lunar-diagnostic-updater'
'ros-lunar-gps-common'
'ros-lunar-nav-msgs'
'ros-lunar-nodelet'
'ros-lunar-novatel-gps-msgs'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
'ros-lunar-std-msgs'
'ros-lunar-swri-math-util'
'ros-lunar-swri-nodelet'
'ros-lunar-swri-roscpp'
'ros-lunar-swri-serial-util'
'ros-lunar-swri-string-util'
'ros-lunar-tf'
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

