SET(VITIK_SRC
        ${PROJECT_SOURCE_DIR}/src/vikit/atan_camera.cpp
        ${PROJECT_SOURCE_DIR}/src/vikit/homography.cpp
        ${PROJECT_SOURCE_DIR}/src/vikit/img_align.cpp
        ${PROJECT_SOURCE_DIR}/src/vikit/math_utils.cpp
        ${PROJECT_SOURCE_DIR}/src/vikit/omni_camera.cpp
        ${PROJECT_SOURCE_DIR}/src/vikit/performance_monitor.cpp
        ${PROJECT_SOURCE_DIR}/src/vikit/pinhole_camera.cpp
        ${PROJECT_SOURCE_DIR}/src/vikit/robust_cost.cpp
        ${PROJECT_SOURCE_DIR}/src/vikit/user_input_thread.cpp
        ${PROJECT_SOURCE_DIR}/src/vikit/vision.cpp
)

SET(SOPHUS_SRC
        ${PROJECT_SOURCE_DIR}/src/sophus/scso3.cpp
        ${PROJECT_SOURCE_DIR}/src/sophus/se2.cpp
        ${PROJECT_SOURCE_DIR}/src/sophus/se3.cpp
        ${PROJECT_SOURCE_DIR}/src/sophus/sim3.cpp
        ${PROJECT_SOURCE_DIR}/src/sophus/so2.cpp
        ${PROJECT_SOURCE_DIR}/src/sophus/so3.cpp
)

include_directories(
        ${EIGEN3_INCLUDE_DIR}
        ${OpenCV_INCLUDE_DIRS}
        ${PROJECT_SOURCE_DIR}/inc/sophus/
        ${PROJECT_SOURCE_DIR}/inc/vikit/
)

ADD_EXECUTABLE(test_vitik_camera test_camera.cpp ${VITIK_SRC} ${SOPHUS_SRC})
ADD_EXECUTABLE(test_vitik_triangulation test_triangulation.cpp ${VITIK_SRC} ${SOPHUS_SRC})
ADD_EXECUTABLE(test_vitik_patchscore test_patch_score.cpp ${VITIK_SRC} ${SOPHUS_SRC})

TARGET_LINK_LIBRARIES(test_vitik_camera ${OpenCV_LIBS} Threads::Threads)
TARGET_LINK_LIBRARIES(test_vitik_triangulation ${OpenCV_LIBS} Threads::Threads)
TARGET_LINK_LIBRARIES(test_vitik_patchscore ${OpenCV_LIBS} Threads::Threads)

ADD_TEST(test_vitik_camera          test_vitik_camera)
ADD_TEST(test_vitik_triangulation   test_vitik_triangulation)
ADD_TEST(test_vitik_patchscore      test_vitik_patchscore)
