cmake_minimum_required(VERSION 2.8)
 
PROJECT(Notepad)
 
find_package(Qt4 REQUIRED)
include(${QT_USE_FILE})

include_directories(${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_BINARY_DIR}) 
 
file(GLOB UI_FILES *.ui)
file(GLOB QT_WRAP *.h)
file(GLOB CPP_FILES *.cpp)
 
QT4_WRAP_UI(UISrcs ${UI_FILES})
QT4_WRAP_CPP(MOCSrcs ${QT_WRAP})

# add the executable
add_executable(Notepad  ${CPP_FILES} ${UISrcs} ${MOCSrcs})
 
target_link_libraries(Notepad ${QT_LIBRARIES})