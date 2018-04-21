# Script generated with Bloom
pkgdesc="ROS - Utility functions for displaying and debugging data in Rviz via published markers"
url='https://github.com/davetcoleman/rviz_visual_tools'

pkgname='ros-kinetic-rviz-visual-tools'
pkgver='3.6.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('qt5-x11extras'
'ros-kinetic-catkin'
'ros-kinetic-eigen-conversions'
'ros-kinetic-eigen-stl-containers'
'ros-kinetic-geometry-msgs'
'ros-kinetic-graph-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-roslint'
'ros-kinetic-rostest'
'ros-kinetic-rosunit'
'ros-kinetic-rviz'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-tf-conversions'
'ros-kinetic-trajectory-msgs'
'ros-kinetic-visualization-msgs'
)

depends=('qt5-x11extras'
'ros-kinetic-eigen-conversions'
'ros-kinetic-eigen-stl-containers'
'ros-kinetic-geometry-msgs'
'ros-kinetic-graph-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-roslint'
'ros-kinetic-rviz'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-tf-conversions'
'ros-kinetic-trajectory-msgs'
'ros-kinetic-visualization-msgs'
)

conflicts=()
replaces=()

_dir=rviz_visual_tools
source=()
md5sums=()

prepare() {
    cp -R $startdir/rviz_visual_tools $srcdir/rviz_visual_tools
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

