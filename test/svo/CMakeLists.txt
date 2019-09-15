SET(SVO_SRC
        ${PROJECT_SOURCE_DIR}/src/svo/frame_handler_mono.cpp
        ${PROJECT_SOURCE_DIR}/src/svo/frame_handler_base.cpp
        ${PROJECT_SOURCE_DIR}/src/svo/frame.cpp
        ${PROJECT_SOURCE_DIR}/src/svo/point.cpp
        ${PROJECT_SOURCE_DIR}/src/svo/map.cpp
        ${PROJECT_SOURCE_DIR}/src/svo/pose_optimizer.cpp
        ${PROJECT_SOURCE_DIR}/src/svo/initialization.cpp
        ${PROJECT_SOURCE_DIR}/src/svo/matcher.cpp
        ${PROJECT_SOURCE_DIR}/src/svo/reprojector.cpp
        ${PROJECT_SOURCE_DIR}/src/svo/feature_alignment.cpp
        ${PROJECT_SOURCE_DIR}/src/svo/feature_detection.cpp
        ${PROJECT_SOURCE_DIR}/src/svo/depth_filter.cpp
        ${PROJECT_SOURCE_DIR}/src/svo/config.cpp
        ${PROJECT_SOURCE_DIR}/src/svo/sparse_img_align.cpp
)

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

SET(FAST_SRC
        ${PROJECT_SOURCE_DIR}/src/fast/fast_10.cpp
        ${PROJECT_SOURCE_DIR}/src/fast/fast_10_score.cpp
        ${PROJECT_SOURCE_DIR}/src/fast/faster_corner_10_sse.cpp
        ${PROJECT_SOURCE_DIR}/src/fast/nonmax_3x3.cpp
)

include_directories(
        ${EIGEN3_INCLUDE_DIR}
        ${OpenCV_INCLUDE_DIRS}
        ${OpenCV_INCLUDE_DIRS}
        ${PROJECT_SOURCE_DIR}/inc/
        ${PROJECT_SOURCE_DIR}/inc/fast/
        ${PROJECT_SOURCE_DIR}/inc/sophus/
        ${PROJECT_SOURCE_DIR}/inc/vikit/
)


ADD_EXECUTABLE(test_depthfilter test_depth_filter.cpp ${SOPHUS_SRC} ${FAST_SRC} ${VITIK_SRC} ${SVO_SRC})
TARGET_LINK_LIBRARIES(test_depthfilter Threads::Threads ${Boost_LIBRARIES} ${OpenCV_LIBS})

ADD_EXECUTABLE(test_featurealignment test_feature_alignment.cpp ${SOPHUS_SRC} ${FAST_SRC} ${VITIK_SRC} ${SVO_SRC})
TARGET_LINK_LIBRARIES(test_featurealignment Threads::Threads ${Boost_LIBRARIES} ${OpenCV_LIBS})

ADD_EXECUTABLE(test_featuredetection test_feature_detection.cpp ${SOPHUS_SRC} ${FAST_SRC} ${VITIK_SRC} ${SVO_SRC})
TARGET_LINK_LIBRARIES(test_featuredetection Threads::Threads ${Boost_LIBRARIES} ${OpenCV_LIBS})

ADD_EXECUTABLE(test_matcher test_matcher.cpp ${SOPHUS_SRC} ${FAST_SRC} ${VITIK_SRC} ${SVO_SRC})
TARGET_LINK_LIBRARIES(test_matcher Threads::Threads ${Boost_LIBRARIES} ${OpenCV_LIBS})

ADD_EXECUTABLE(test_pipeline test_pipeline.cpp ${SOPHUS_SRC} ${FAST_SRC} ${VITIK_SRC} ${SVO_SRC})
TARGET_LINK_LIBRARIES(test_pipeline Threads::Threads ${Boost_LIBRARIES} ${OpenCV_LIBS})

ADD_EXECUTABLE(test_poseoptimizer test_pose_optimizer.cpp ${SOPHUS_SRC} ${FAST_SRC} ${VITIK_SRC} ${SVO_SRC})
TARGET_LINK_LIBRARIES(test_poseoptimizer Threads::Threads ${Boost_LIBRARIES} ${OpenCV_LIBS})

ADD_EXECUTABLE(test_sparseimagealign test_sparse_img_align.cpp ${SOPHUS_SRC} ${FAST_SRC} ${VITIK_SRC} ${SVO_SRC})
TARGET_LINK_LIBRARIES(test_sparseimagealign Threads::Threads ${Boost_LIBRARIES} ${OpenCV_LIBS})
