add_library(sdcard STATIC
        emmc.cpp
        mmchost.cpp
        sdhost.cpp)
target_link_libraries(sdcard circle)
