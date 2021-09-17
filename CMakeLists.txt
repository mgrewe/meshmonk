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



add_executable(meshmonk_registration_ssm meshmonk_registration_ssm.cpp meshmonk.cpp ${SRCS})
target_include_directories(meshmonk_registration_ssm PUBLIC src vendor)
target_include_directories(meshmonk_registration_ssm PUBLIC ${EIGEN3_INCLUDE_DIR} ${OPENMESH_INCLUDE_DIRS})
target_link_libraries(meshmonk_registration_ssm OpenMeshCore OpenMeshTools)



add_executable(meshmonk_registration_bfm meshmonk_registration_bfm.cpp meshmonk.cpp ${SRCS})
target_include_directories(meshmonk_registration_bfm PUBLIC src vendor)
target_include_directories(meshmonk_registration_bfm PUBLIC ${EIGEN3_INCLUDE_DIR} ${OPENMESH_INCLUDE_DIRS})
target_link_libraries(meshmonk_registration_bfm OpenMeshCore OpenMeshTools)

