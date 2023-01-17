cmake_minimum_required(VERSION 3.10)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}" ${CMAKE_MODULE_PATH})

find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)
find_package(OpenCV REQUIRED)
find_package (glfw3 REQUIRED)
find_package(GLEW REQUIRED)


find_library(GTK_LIB libgtk-3.so PATHS /usr/lib/x86_64-linux-gnu NO_DEFAULT_PATH)
find_library(GLIB libglib-2.0.so PATHS /usr/lib/x86_64-linux-gnu NO_DEFAULT_PATH)

add_executable(main matRender.cpp )

include_directories(main PUBLIC
    ${OPENGL_INCLUDE_DIRS}  
    ${GLUT_INCLUDE_DIRS} 
    /usr/include/gtk-3.0
	/usr/include/glib-2.0
    /usr/include/pango-1.0
    /usr/include/cairo
	/usr/include/gdk-pixbuf-2.0
    /usr/include/atk-1.0
    /usr/lib/x86_64-linux-gnu/glib-2.0/include
)




target_link_libraries(main 
    ${GLFW3_LIBRARY}
    ${OPENGL_LIBRARIES} 
    ${GLUT_LIBRARY}
    ${OpenCV_LIBS}
    ${GTK_LIB}
    ${GLIB}
    /usr/lib/x86_64-linux-gnu/libglib-2.0.so
	/usr/lib/x86_64-linux-gnu/libgdk-3.so
	/usr/lib/x86_64-linux-gnu/libcairo.so
	/usr/lib/x86_64-linux-gnu/libgobject-2.0.so
	/usr/lib/x86_64-linux-gnu/libglib-2.0.a
	/usr/lib/x86_64-linux-gnu/libpcre.so
    glfw 
    GLEW::GLEW
    )