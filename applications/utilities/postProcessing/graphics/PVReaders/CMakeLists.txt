CMAKE_MINIMUM_REQUIRED(VERSION 3.5.1)

PROJECT(PVReaders)

FIND_PACKAGE(ParaView REQUIRED)

INCLUDE(GNUInstallDirs)

SET(BUILD_SHARED_LIBS ON)

PARAVIEW_PLUGIN_SCAN(
    PLUGIN_FILES
        "PVblockMeshReader/paraview.plugin"
        "PVFoamReader/paraview.plugin"
    PROVIDES_PLUGINS plugins
    ENABLE_BY_DEFAULT ON
)

PARAVIEW_PLUGIN_BUILD(PLUGINS ${plugins})
