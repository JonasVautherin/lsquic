cmake_minimum_required(VERSION 2.8)

project(external-openssl)
include(ExternalProject)

message(STATUS "Preparing external project \"openssl\"")

ExternalProject_add(
    openssl
    GIT_REPOSITORY https://github.com/akamai/openssl
    GIT_TAG master-quic-support
    PREFIX openssl
    CONFIGURE_COMMAND <SOURCE_DIR>/config $ENV{OPENSSL_PLATFORM} --prefix=${CMAKE_INSTALL_PREFIX} no-shared
    )
