build_elf(sample-fatfs main.cpp kernel.cpp)
target_link_libraries(sample-fatfs sdcard usb input fs fatfs)
