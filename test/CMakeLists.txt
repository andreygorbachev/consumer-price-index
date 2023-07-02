project(consumer-price-index-test)
#project(test)

include(FetchContent)
FetchContent_Declare(
  rapidcsv
  GIT_REPOSITORY https://github.com/d99kris/rapidcsv.git
  GIT_TAG        v8.75
)
FetchContent_MakeAvailable(rapidcsv)

include(FetchContent)
FetchContent_Declare(
  googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG        v1.13.0
)
FetchContent_MakeAvailable(googletest)

add_executable(${PROJECT_NAME}
  daily_index.cpp
)

target_link_libraries(${PROJECT_NAME} PRIVATE
  consumer-price-index
  Calendar::calendar
  CouponSchedule::coupon-schedule
  Reset::reset
  rapidcsv
  GTest::gtest_main
)

include(GoogleTest)
gtest_discover_tests(${PROJECT_NAME}
  WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/data
)
