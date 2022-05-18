### Unit tests
#
#   Only configured when CATKIN_ENABLE_TESTING is true.

# C++ gtests
find_package(ament_cmake_pytest)
find_package(ament_cmake_gtest)

ament_add_gtest (test_${PROJECT_NAME}
                 test_${PROJECT_NAME}.cpp
                 second_test_${PROJECT_NAME}.cpp)
# add_dependencies(test_${PROJECT_NAME} ${ament_EXPORTED_TARGETS})
target_link_libraries(test_${PROJECT_NAME}
                      ${Boost_LIBRARIES}
                      # ${ament_LIBRARIES}
                      )

# Python nose tests
ament_add_pytest_test(test_${PROJECT_NAME}_py test_${PROJECT_NAME}.py)
