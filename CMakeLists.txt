cmake_minimum_required(VERSION 2.6)

include(ReMake)

remake_project(
  starleth-init
  VERSION 0.1
  RELEASE alpha
  SUMMARY "A collection of system startup scripts for the StarlETH robot."
  AUTHOR "Jerome Maye"
  CONTACT "jerome.maye@mavt.ethz.ch"
  HOME "http://github.com/jmaye/starleth-init"
  LICENSE "GNU Lesser General Public License (LGPL)"
  PREFIX starleth-
  INSTALL /usr
  SCRIPT_DESTINATION /etc
  CONFIGURATION_DESTINATION /etc/starleth
)

remake_pack_deb(
  ARCH all
  DEPENDS lsb-base base-files
  EXTRA debian/*
)

remake_distribute_deb(
  DISTRIBUTION lucid
  SECTION admin
  UPLOAD ppa:jmaye/starleth
  DEPENDS remake lsb-base base-files
  PASS STARLETH_INIT_GIT_REVISION
)

remake_distribute_deb(
  DISTRIBUTION precise
  SECTION admin
  UPLOAD ppa:jmaye/starleth
  DEPENDS remake lsb-base base-files
  PASS STARLETH_INIT_GIT_REVISION
)

remake_distribute_deb(
  DISTRIBUTION trusty
  SECTION admin
  UPLOAD ppa:jmaye/starleth
  DEPENDS remake lsb-base base-files
  PASS STARLETH_INIT_GIT_REVISION
)
