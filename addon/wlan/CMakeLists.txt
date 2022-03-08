add_subdirectory(hostap/wpa_supplicant)
add_library(wlan
        bcm4343.cpp ether4330.c emmc.c
        p9arch.cpp p9chan.cpp p9cmd.cpp p9error.cpp p9ether.cpp p9proc.cpp p9util.cpp
)
target_link_libraries(wlan circle wpa_supplicant)
