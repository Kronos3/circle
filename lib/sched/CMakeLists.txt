add_library(sched mutex.cpp
        scheduler.cpp
        semaphore.cpp
        synchronizationevent.cpp
        task.cpp
        taskswitch.S)
target_link_libraries(sched circle)
