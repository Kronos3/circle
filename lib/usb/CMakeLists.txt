set(USB_SRCS
        lan7800.cpp smsc951x.cpp usbbluetooth.cpp usbcdcethernet.cpp
        usbconfigparser.cpp usbdevice.cpp usbdevicefactory.cpp usbendpoint.cpp usbfunction.cpp
        usbgamepad.cpp usbgamepadps3.cpp usbgamepadps4.cpp usbgamepadstandard.cpp usbgamepadswitchpro.cpp
        usbgamepadxbox360.cpp usbgamepadxboxone.cpp usbhiddevice.cpp usbhostcontroller.cpp
        usbkeyboard.cpp usbmassdevice.cpp usbmidi.cpp usbmouse.cpp usbprinter.cpp usbrequest.cpp
        usbstandardhub.cpp usbstring.cpp usbserial.cpp usbserialch341.cpp usbserialcp2102.cpp
        usbserialpl2303.cpp usbserialft231x.cpp usbserialcdc.cpp usbtouchscreen.cpp
)

if (NOT (RASPPI EQUAL 4))
    set(USB_SRCS ${USB_SRCS}
            dwhcidevice.cpp dwhciframeschednper.cpp dwhciframeschednsplit.cpp dwhciframeschedper.cpp
            dwhciregister.cpp dwhcirootport.cpp dwhcixactqueue.cpp dwhcixferstagedata.cpp)
else()
    set(USB_SRCS ${USB_SRCS}
            xhcicommandmanager.cpp xhcidevice.cpp xhciendpoint.cpp xhcieventmanager.cpp xhcimmiospace.cpp
            xhciring.cpp xhciroothub.cpp xhcirootport.cpp xhcisharedmemallocator.cpp xhcislotmanager.cpp
            xhciusbdevice.cpp)
endif()

add_library(usb STATIC ${USB_SRCS})
target_link_libraries(usb circle)
