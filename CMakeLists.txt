cmake_minimum_required(VERSION 3.15)

project("consumer-price-index" VERSION 0.0)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED On)
set(CMAKE_CXX_EXTENSIONS Off)

find_package(Calendar)
find_package(CouponSchedule)
find_package(Reset)

enable_testing()

add_subdirectory(include)
add_subdirectory(test)
