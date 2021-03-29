cmake_minimum_required(VERSION 3.10)

project(meshmonk)


file( GLOB SRCS src/*.cpp)

find_package(OpenMesh REQUIRED)
find_package(Eigen3 REQUIRED)

# add_library(meshmonk STATIC meshmonk.cpp ${SRCS})
# target_link_libraries(meshmonk ${OpenMesh_LIBS} OpenMeshCore OpenMeshTools)
# target_include_directories(meshmonk PUBLIC vendor)
# target_include_directories(meshmonk PUBLIC ${EIGEN3_INCLUDE_DIR} ${OPENMESH_INCLUDE_DIRS})


add_executable(meshmonk_registration meshmonk_registration.cpp meshmonk.cpp ${SRCS})
target_include_directories(meshmonk_registration PUBLIC src vendor)
target_include_directories(meshmonk_registration PUBLIC ${EIGEN3_INCLUDE_DIR} ${OPENMESH_INCLUDE_DIRS})
target_link_libraries(meshmonk_registration OpenMeshCore OpenMeshTools)


# target_link_libraries(write_text opencv_imgcodecs opencv_core opencv_imgproc)