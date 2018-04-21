# Script generated with Bloom
pkgdesc="ROS - The naoqi_bridge_msgs package provides custom messages for running Aldebaran's robot such as NAO and Pepper. See the packages nao_robot and pepper_robot for details."


pkgname='ros-kinetic-naoqi-bridge-msgs'
pkgver='0.0.8_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-actionlib-msgs'
'ros-kinetic-catkin'
'ros-kinetic-genmsg'
'ros-kinetic-geometry-msgs'
'ros-kinetic-message-generation'
'ros-kinetic-nav-msgs'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-trajectory-msgs'
)

depends=('ros-kinetic-actionlib-msgs'
'ros-kinetic-genmsg'
'ros-kinetic-geometry-msgs'
'ros-kinetic-message-runtime'
'ros-kinetic-nav-msgs'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-trajectory-msgs'
)

conflicts=('ros-kinetic-naoqi-msgs'
)
replaces=('ros-kinetic-naoqi-msgs'
)

_dir=naoqi_bridge_msgs
source=()
md5sums=()

prepare() {
    cp -R $startdir/naoqi_bridge_msgs $srcdir/naoqi_bridge_msgs
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

