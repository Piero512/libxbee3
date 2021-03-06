cmake_minimum_required(VERSION 3.0)
project(xbee3 C)

set(CMAKE_CXX_STANDARD 11)
find_package(Threads REQUIRED)

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(include)

add_compile_definitions(XBEE_NO_NET_SERVER)
add_library(xbee SHARED
        include/xbee.h
        include/xbeep.h
        modes/debug/mode.c
        modes/debug/mode.h
        modes/xbee1/at.c
        modes/xbee1/at.h
        modes/xbee1/data.c
        modes/xbee1/data.h
        modes/xbee1/io.c
        modes/xbee1/io.h
        modes/xbee1/mode.c
        modes/xbee1/mode.h
        modes/xbee2/at.c
        modes/xbee2/at.h
        modes/xbee2/data.c
        modes/xbee2/data.h
        modes/xbee2/dataExp.c
        modes/xbee2/dataExp.h
        modes/xbee2/identify.c
        modes/xbee2/identify.h
        modes/xbee2/io.c
        modes/xbee2/io.h
        modes/xbee2/mode.c
        modes/xbee2/mode.h
        modes/xbee2/sensor.c
        modes/xbee2/sensor.h
        modes/xbee3/at.c
        modes/xbee3/at.h
        modes/xbee3/data.c
        modes/xbee3/data.h
        modes/xbee3/dataExp.c
        modes/xbee3/dataExp.h
        modes/xbee3/identify.c
        modes/xbee3/identify.h
        modes/xbee3/io.c
        modes/xbee3/io.h
        modes/xbee3/mode.c
        modes/xbee3/mode.h
        modes/xbee5/at.c
        modes/xbee5/at.h
        modes/xbee5/data.c
        modes/xbee5/data.h
        modes/xbee5/dataExp.c
        modes/xbee5/dataExp.h
        modes/xbee5/identify.c
        modes/xbee5/identify.h
        modes/xbee5/io.c
        modes/xbee5/io.h
        modes/xbee5/mode.c
        modes/xbee5/mode.h
        modes/xbee6b/at.c
        modes/xbee6b/at.h
        modes/xbee6b/data.c
        modes/xbee6b/data.h
        modes/xbee6b/io.c
        modes/xbee6b/io.h
        modes/xbee6b/mode.c
        modes/xbee6b/mode.h
        modes/xbeeZB/at.c
        modes/xbeeZB/at.h
        modes/xbeeZB/data.c
        modes/xbeeZB/data.h
        modes/xbeeZB/dataExp.c
        modes/xbeeZB/dataExp.h
        modes/xbeeZB/identify.c
        modes/xbeeZB/identify.h
        modes/xbeeZB/io.c
        modes/xbeeZB/io.h
        modes/xbeeZB/mode.c
        modes/xbeeZB/mode.h
        modes/xbeeZB/ota.c
        modes/xbeeZB/ota.h
        modes/xbeeZB/route.c
        modes/xbeeZB/route.h
        modes/xbeeZB/sensor.c
        modes/xbeeZB/sensor.h
        modes/common.c
        modes/common.h
        xsys_darwin/sem_timedwait.c
        xsys_darwin/sem_timedwait.h
        conn.c
        conn.h
        error.c
        frame.c
        frame.h
        internal.h
        ll.c
        ll.h
        log.c
        log.h
        mode.c
        mode.h
        mutex.c
        mutex.h
        pkt.c
        pkt.h
        prepare.c
        prepare.h
        rx.c
        rx.h
        thread.c
        thread.h
        tx.c
        tx.h
        ver.c
        xbee.c
        xbee_int.h
        xbeep.cpp
        xsys.c
        xsys.h)
target_link_libraries(xbee Threads::Threads)
install(TARGETS xbee DESTINATION lib)
FILE(GLOB headers "${CMAKE_CURRENT_SOURCE_DIR}/include/*.h")
install(FILES ${headers} DESTINATION include)
