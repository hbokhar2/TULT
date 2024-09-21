cmake_minimum_required(VERSION 3.10)
project(TULT)

add_executable(TULT src/main.c)

find_package(CURL REQUIRED)
target_link_libraries(TULT ${CURL_LIBRARIES} -static)

#GTK has poor windows support so this will be linked statically 
find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK REQUIRED gtk+-3.0)
target_link_libraries(TULT ${GTK_LIBRARIES})
target_include_directories(TULT PRIVATE ${GTK_INCLUDE_DIRS})