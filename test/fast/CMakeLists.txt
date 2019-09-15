SET(FAST_SRC
        ${PROJECT_SOURCE_DIR}/src/fast/fast_10.cpp
        ${PROJECT_SOURCE_DIR}/src/fast/fast_10_score.cpp
        ${PROJECT_SOURCE_DIR}/src/fast/faster_corner_10_sse.cpp
        ${PROJECT_SOURCE_DIR}/src/fast/nonmax_3x3.cpp
        )

include_directories(
        ${EIGEN3_INCLUDE_DIR}
        ${OpenCV_INCLUDE_DIRS}
        ${PROJECT_SOURCE_DIR}/inc/fast/)

ADD_EXECUTABLE(test_fast    ${PROJECT_SOURCE_DIR}/test/fast/test.cpp    ${FAST_SRC})
TARGET_LINK_LIBRARIES(test_fast ${OpenCV_LIBS})

ADD_TEST(test_fast  test_fast)