SET(SOPHUS_SRC
        ${PROJECT_SOURCE_DIR}/src/sophus/scso3.cpp
        ${PROJECT_SOURCE_DIR}/src/sophus/se2.cpp
        ${PROJECT_SOURCE_DIR}/src/sophus/se3.cpp
        ${PROJECT_SOURCE_DIR}/src/sophus/sim3.cpp
        ${PROJECT_SOURCE_DIR}/src/sophus/so2.cpp
        ${PROJECT_SOURCE_DIR}/src/sophus/so3.cpp)

include_directories(
        ${EIGEN3_INCLUDE_DIR}
        ${OpenCV_INCLUDE_DIRS}
        ${PROJECT_SOURCE_DIR}/inc/sophus/)

ADD_EXECUTABLE(test_sophus_so2      ${PROJECT_SOURCE_DIR}/test/sophus/test_so2.cpp    ${SOPHUS_SRC})
ADD_EXECUTABLE(test_sophus_se2      ${PROJECT_SOURCE_DIR}/test/sophus/test_se2.cpp    ${SOPHUS_SRC})
ADD_EXECUTABLE(test_sophus_so3      ${PROJECT_SOURCE_DIR}/test/sophus/test_so3.cpp    ${SOPHUS_SRC})
ADD_EXECUTABLE(test_sophus_scso3    ${PROJECT_SOURCE_DIR}/test/sophus/test_scso3.cpp  ${SOPHUS_SRC})
ADD_EXECUTABLE(test_sophus_se3      ${PROJECT_SOURCE_DIR}/test/sophus/test_se3.cpp    ${SOPHUS_SRC})
ADD_EXECUTABLE(test_sophus_sim3     ${PROJECT_SOURCE_DIR}/test/sophus/test_sim3.cpp   ${SOPHUS_SRC})

ADD_TEST(test_sophus_so2            test_sophus_so2  )
ADD_TEST(test_sophus_se2            test_sophus_se2  )
ADD_TEST(test_sophus_so3            test_sophus_so3  )
ADD_TEST(test_sophus_scso3          test_sophus_scso3)
ADD_TEST(test_sophus_se3            test_sophus_se3  )
ADD_TEST(test_sophus_sim3           test_sophus_sim3 )