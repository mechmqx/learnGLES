cmake_minimum_required(VERSION 2.6)
project(testGLFW)

set (OPENGLES3_LIBRARY ${CMAKE_SOURCE_DIR}/GLESv30/lib/mali-opengl-es-emulator/libGLESv2.so)
set (EGL_LIBRARY ${CMAKE_SOURCE_DIR}/GLESv30/lib/mali-opengl-es-emulator/libEGL.so)

set(GLFWLIB ${CMAKE_SOURCE_DIR}/glfw3/lib/libglfw3.a)
set(GLFW_INLCUDEPATH ${CMAKE_SOURCE_DIR}/glfw3/include)

set(DEP_PATH ${CMAKE_SOURCE_DIR}/deps)
include_directories(${GLFW_INLCUDEPATH} ${DEP_PATH})


add_executable(testGLFW ${CMAKE_SOURCE_DIR}/src/simple.c ${DEP_PATH}/glad.c)
target_link_libraries(testGLFW ${OPENGLES3_LIBRARY} ${EGL_LIBRARY} ${GLFWLIB} -lm -ldl -lpthread -lX11)
