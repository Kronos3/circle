add_library(fatfs
        diskio.cpp
        diskio.h
        ff.c
        ff.h
        ffconf.h
        ffsystem.cpp
        ffunicode.c)
target_link_libraries(fatfs sdcard usb fs circle)
