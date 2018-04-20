# Script generated with Bloom
pkgdesc="ROS - Driver package for Wacohtech dynpick force sensor. This contains <a href="http://ros.org/">ROS</a>-compatible linux driver, as well as a communication test tool.<br/> As of Oct 2016, it's tested with the following models of dynpick: <ul> <li><a href="http://www.wacoh-tech.com/products/dynpick/wdf-6m200-3.html">wdf-6m200-3</a></li> <li><a href="http://www.wacoh-tech.com/en/products/dynpick/200n.html">WEF-6A200</a> (confirmed <a href="https://github.com/tork-a/dynpick_driver/pull/35#issuecomment-256031851">here</a>)</li> </ul>"
url='http://wiki.ros.org/dynpick_driver'

pkgname='ros-lunar-dynpick-driver'
pkgver='0.2.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('python2-catkin_pkg'
'ros-lunar-catkin'
'ros-lunar-geometry-msgs'
'ros-lunar-roscpp'
'ros-lunar-rostest'
'ros-lunar-std-srvs'
)

depends=('ros-lunar-geometry-msgs'
'ros-lunar-robot-state-publisher'
'ros-lunar-roscpp'
'ros-lunar-rviz'
'ros-lunar-std-srvs'
'ros-lunar-tf'
'ros-lunar-xacro'
)

conflicts=()
replaces=()

_dir=dynpick_driver
source=()
md5sums=()

prepare() {
    cp -R $startdir/dynpick_driver $srcdir/dynpick_driver
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

