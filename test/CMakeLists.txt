cmake_minimum_required (VERSION 3.10.2)
add_executable(${PROJECT_NAME}.test
  AllTests.cpp
  tests.cpp)
target_link_libraries(${PROJECT_NAME}.test
  ${PROJECT_NAME} gtest pthread)
target_compile_definitions(${PROJECT_NAME}.test 
  PRIVATE TEST_DIR="${CMAKE_CURRENT_LIST_DIR}/test")

install(TARGETS ${PROJECT_NAME}.test
        DESTINATION "${tool_dest}")

file(COPY ${PROJECT_SOURCE_DIR}/src/war_peace.txt DESTINATION "/home/runner/work/ADS-8/ADS-8/build/test")
