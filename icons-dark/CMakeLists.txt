project(breath2-dark-icons NONE)

cmake_minimum_required(VERSION 2.8)
# include specific modules
set (CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake")

if (WIN32)
   set(ICON_INSTALL_DIR         "share/icons"             ) # The icon install dir (default ${SHARE_INSTALL_PREFIX}/share/icons/)
else (WIN32)
   set(SHARE_INSTALL_PREFIX "${CMAKE_INSTALL_PREFIX}/share" )
   set(ICON_INSTALL_DIR     "${SHARE_INSTALL_PREFIX}/icons" )
endif(WIN32)

########### install files ###############

set( breath2_icon_dirs actions applets apps categories devices emblems emotes mimetypes places preferences status)


set(BREATH2_INSTALL_DIR ${ICON_INSTALL_DIR}/breath2-dark)
install( DIRECTORY ${breath2_icon_dirs} DESTINATION ${BREATH2_INSTALL_DIR} PATTERN "*.sh" EXCLUDE )
install( FILES index.theme DESTINATION ${BREATH2_INSTALL_DIR})
