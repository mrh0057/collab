cmake_minimum_required(VERSION 2.8)

SET(CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake ${CMAKE_MODULE_PATH})

PROJECT( collab )

ADD_DEFINITIONS( -Wall -g)

# this command finds Qt4 libraries and sets all required variables
# note that it's Qt4, not QT4 or qt4
FIND_PACKAGE( Qt4 REQUIRED )

# add some useful macros and variables
# (QT_USE_FILE is a variable defined by FIND_PACKAGE( Qt4 ) that contains a path to CMake script)
INCLUDE( ${QT_USE_FILE} )

INCLUDE_DIRECTORIES(${QT_QTTEST_INCLUDE_DIR} ${QT_QTNETWORK_INCLUDE_DIR})

SET(QT_USE_QTTEST  true)

SET(LIBRARIES ${QT_LIBRARIES} ${QT_QTNETWORK_LIBARIES} ${HUNSPELL_LIBRARIES})

add_subdirectory(src)
#add_subdirectory(test)
