add_library(fat STATIC
        fatfs.cpp fatcache.cpp fatinfo.cpp fat.cpp fatdir.cpp
)
target_link_libraries(fat fs circle)
