project("consumer-price-index")

add_library(${PROJECT_NAME} INTERFACE
  daily_index.h
)

target_include_directories(${PROJECT_NAME} INTERFACE .)
