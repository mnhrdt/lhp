
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR}/bin)

# internal includes
include_directories(${CMAKE_SOURCE_DIR})
include_directories(${CMAKE_SOURCE_DIR}/utils)
include_directories(${CMAKE_SOURCE_DIR}/core)

# external excludes
#include_directories(${CBLAS_INCLUDE_DIR})
include_directories(${IIO_INCLUDE_DIR})

add_executable(vnlbayes main_vnlb.cpp)

#link_directories(${CMAKE_BINARY_DIR}/lib)
target_link_libraries(vnlbayes videoNlBayes ${CBLAS_LIBRARIES})

# These are not necessary
# ${IIO_LIBRARIES})

