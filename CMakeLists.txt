project(chapterFirstExample)
cmake_minimum_required(VERSION 3.2)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_FLAGS "${CMAXE_CXX_FLAGS} -Wall")

enable_testing()

set(sources
    main.cpp)

set(testSources
    soundex_test.cpp)


add_executable(soundex_test ${testSources}  ${sources})

target_link_libraries(soundex_test gmock)
target_link_libraries(soundex_test gtest)
target_link_libraries(soundex_test pthread)

include(GoogleTest)
gtest_discover_tests(soundex_test)
