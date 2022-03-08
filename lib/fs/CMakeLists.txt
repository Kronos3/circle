add_subdirectory(fat)

add_library(fs partition.cpp partitionmanager.cpp)
target_link_libraries(fs circle)
