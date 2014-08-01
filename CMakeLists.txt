cmake_minimum_required (VERSION 2.6)
project (SOIL)

find_package (OpenGL REQUIRED)
include_directories (${OPENGL_INCLUDE_DIR})

file (GLOB SOIL_SOURCES src/*.c)
file (GLOB SOIL_HEADERS src/*.h)

add_library(${PROJECT_NAME} STATIC ${SOIL_SOURCES})

if(APPLE)
	target_link_libraries (SOIL ${OPENGL_LIBRARIES} "-framework CoreFoundation")
elseif(APPLE)
	target_link_libraries (SOIL ${OPENGL_LIBRARIES})
endif(APPLE)
