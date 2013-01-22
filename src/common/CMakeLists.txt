FILE(GLOB Sources *.cpp) 
FILE(GLOB Mocs *.h)
FILE(GLOB UI *.ui)

QT4_WRAP_UI(UIS_H ${UI})

QT4_WRAP_CPP(MOC_SRCS ${Mocs})

include_directories(${CMAKE_CURRENT_BINARY_DIR})

add_library(collab-common ${Mocs} ${UI} ${MOC_SRCS} ${Sources}) 