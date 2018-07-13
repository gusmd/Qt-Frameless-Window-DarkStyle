cmake_minimum_required(VERSION 3.2)

project(QtFramelessWindowDarkStyle)

set(DARKSTYLE_INCLUDE
    framelesswindow/framelesswindow.h
    framelesswindow/windowdragger.h
    DarkStyle.h
)

set(DARKSTYLE_SRC
    framelesswindow/framelesswindow.cpp
    framelesswindow/windowdragger.cpp
    DarkStyle.cpp
)

set(DARKSTYLE_RC
    darkstyle.qrc
    framelesswindow.qrc
)

add_library(QtFramelessWindowDarkStyle STATIC ${DARKSTYLE_INCLUDE} ${DARKSTYLE_SRC} ${DARKSTYLE_RC})

set_target_properties(QtFramelessWindowDarkStyle
    PROPERTIES
    CXX_STANDARD 11
    CXX_EXTENSIONS OFF
    AUTOMOC ON
    AUTOUIC ON
    AUTORCC ON
)

target_include_directories(QtFramelessWindowDarkStyle PUBLIC . framelesswindow)

find_package(Qt5 COMPONENTS Widgets REQUIRED)
target_link_libraries(QtFramelessWindowDarkStyle PUBLIC Qt5::Widgets)