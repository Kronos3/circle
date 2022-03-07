add_library(net STATIC
        netsubsystem.cpp nettask.cpp netsocket.cpp socket.cpp
        transportlayer.cpp networklayer.cpp linklayer.cpp netdevlayer.cpp phytask.cpp arphandler.cpp
        icmphandler.cpp routecache.cpp
        netconnection.cpp udpconnection.cpp
        tcpconnection.cpp retransmissionqueue.cpp retranstimeoutcalc.cpp tcprejector.cpp
        netconfig.cpp ipaddress.cpp netqueue.cpp checksumcalculator.cpp
        dnsclient.cpp ntpclient.cpp mqttclient.cpp mqttsendpacket.cpp mqttreceivepacket.cpp
        dhcpclient.cpp ntpdaemon.cpp httpdaemon.cpp httpclient.cpp tftpdaemon.cpp syslogdaemon.cpp
)
target_link_libraries(net circle)
