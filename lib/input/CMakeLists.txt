add_library(input STATIC 
        keyboardbehaviour.cpp keymap.cpp mousebehaviour.cpp mouse.cpp touchscreen.cpp rpitouchscreen.cpp
        console.cpp keyboardbuffer.cpp linediscipline.cpp
)
target_link_libraries(input circle)
