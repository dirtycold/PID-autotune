cmake_minimum_required(VERSION 3.8)

project(PID-autotune)

find_package(Qt5 COMPONENTS Core Widgets PrintSupport REQUIRED)
set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)


file(
	GLOB
	source_files
	src/*.cpp
	third_party/qcustomplot/*.cpp
)

file(
	GLOB
	header_files
	src/*.hpp
	third_party/qcustomplot/*.h
)

add_executable(
	pid-autotune
	${source_files}
        ${header_files}
)

target_link_libraries(
	pid-autotune
        Qt5::Core
        Qt5::Widgets
        Qt5::PrintSupport
)
