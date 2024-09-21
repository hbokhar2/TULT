cmake_minimum_required(VERSION 3.10)
project(TULT)

find_package(CURL REQUIRED)

add_executable(TULT src/main.c)
target_link_libraries(TULT ${CURL_LIBRARIES})
target_include_directories(TULT PRIVATE ${CURL_INCLUDE_DIRS})