set(CIRCLE_SRCS
        actled.cpp alloc.cpp assert.cpp bcmframebuffer.cpp bcmmailbox.cpp
        bcmpropertytags.cpp bcmwatchdog.cpp chargenerator.cpp classallocator.cpp
        cputhrottle.cpp debug.cpp delayloop.S device.cpp devicenameservice.cpp
        dmachannel.cpp dmasoundbuffers.cpp gpioclock.cpp gpiomanager.cpp gpiopin.cpp gpiopinfiq.cpp
        i2cmaster.cpp i2cslave.cpp hdmisoundbasedevice.cpp i2ssoundbasedevice.cpp koptions.cpp
        logger.cpp machineinfo.cpp multicore.cpp nulldevice.cpp ptrarray.cpp ptrlist.cpp
        pwmoutput.cpp pwmsoundbasedevice.cpp pwmsounddevice.cpp qemu.cpp screen.cpp serial.cpp
        soundbasedevice.cpp spimaster.cpp spimasteraux.cpp spimasterdma.cpp spinlock.cpp
        string.cpp sysinit.cpp time.cpp timer.cpp tracer.cpp usertimer.cpp util.cpp
        util_fast.S virtualgpiopin.cpp chainboot.cpp macaddress.cpp netdevice.cpp
        new.cpp heapallocator.cpp pageallocator.cpp setjmp.S numberpool.cpp
        latencytester.cpp writebuffer.cpp 2dgraphics.cpp
)

if (AARCH EQUAL 32)
    set(CIRCLE_SRCS ${CIRCLE_SRCS}
            cache-v7.S exceptionhandler.cpp exceptionstub.S memory.cpp pagetable.cpp
            startup.S synchronize.cpp
    )
else()
    set(CIRCLE_SRCS ${CIRCLE_SRCS}
            exceptionhandler64.cpp exceptionstub64.S memory64.cpp startup64.S
            synchronize64.cpp translationtable64.cpp
    )
endif()

if(AARCH EQUAL 32)
    if(STDLIB_SUPPORT EQUAL 0)
        set(CIRCLE_SRCS ${CIRCLE_SRCS} libhelper.cpp libstub.S)
    endif()
endif()

if(NOT (RASPPI EQUAL 4))
    set(CIRCLE_SRCS ${CIRCLE_SRCS} bcmrandom.cpp interrupt.cpp)
else()
    set(CIRCLE_SRCS ${CIRCLE_SRCS}
            cm54213.o bcmpciehostbridge.o bcmrandom200.o interruptgic.o dma4channel.o
            devicetreeblob.o)
endif()

if (STDLIB_SUPPORT EQUAL 3)
    set(CIRCLE_SRCS ${CIRCLE_SRCS} purecall.cpp cxa_guard.cpp)
endif()

add_library(circle STATIC ${CIRCLE_SRCS})

add_subdirectory(fs)
add_subdirectory(input)
add_subdirectory(net)
add_subdirectory(sched)
add_subdirectory(usb)
