build_elf(wlan-test
        kernel.cpp main.cpp
)
target_link_libraries(wlan-test
        wlan usb fatfs sdcard net sched input fs)
