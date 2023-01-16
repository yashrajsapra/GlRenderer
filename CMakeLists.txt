cmake_minimum_required(VERSION 3.10)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}" ${CMAKE_MODULE_PATH})
find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)
find_package(OpenCV REQUIRED)
find_package (glfw3 REQUIRED)
find_package(GLEW REQUIRED)
include_directories( ${OPENGL_INCLUDE_DIRS}  ${GLUT_INCLUDE_DIRS} )



add_executable(main matRender.cpp )
target_link_libraries(main 
    ${GLFW3_LIBRARY}
    ${OPENGL_LIBRARIES} 
    ${GLUT_LIBRARY}
    ${OpenCV_LIBS}
    glfw 
    GLEW::GLEW)