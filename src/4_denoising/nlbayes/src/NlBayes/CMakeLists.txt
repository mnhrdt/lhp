
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR}/lib)
include_directories(${CMAKE_SOURCE_DIR}/src/Utilities)
include_directories(${IIO_INCLUDE_DIR})

add_library(videoNlBayes SHARED
	VideoNLBayes.cpp
	LibMatrix.cpp
	../Utilities/LibImages.cpp
	../Utilities/LibVideoT.cpp
	../Utilities/mt19937ar.c
	../Utilities/Utilities.cpp
	)

target_link_libraries(videoNlBayes iio)

set_target_properties(videoNlBayes PROPERTIES
	SOVERSION ${PROJECT_VERSION})

install(TARGETS videoNlBayes
    LIBRARY DESTINATION lib
    COMPONENT libs)
