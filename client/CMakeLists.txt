cmake_minimum_required(VERSION 3.20.0 FATAL_ERROR)

project(docolechat-server)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)


add_executable(docolechat-client)

find_package(Boost )
find_package(Qt5 COMPONENTS Core Widgets )

set(sources 
	src/main.cpp
        src/chat_message.hpp
        src/mainwindow.h
        src/mainwindow.cpp
        src/mainwindow.ui
    )

target_sources(docolechat-client PRIVATE ${sources})
target_include_directories(docolechat-client 
	PRIVATE
		src)

target_link_libraries(docolechat-client PRIVATE Boost::boost Qt5::Core Qt5::Widgets)
