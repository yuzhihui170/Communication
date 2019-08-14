# For more information about using CMake with Android Studio, read the
# documentation: https://d.android.com/studio/projects/add-native-code.html

# Sets the minimum version of CMake required to build the native library.

cmake_minimum_required(VERSION 3.4.1)

include_directories(src/main/jni)
include_directories(src/main/jni/jthread)
include_directories(src/main/jni/JRTPLIB/src)
include_directories(src/main/jni/ffmpeg/include)

add_library(# Sets the name of the library.
            jrtplib

            # Sets the library as a shared library.
            SHARED

            # Provides a relative path to your source file(s).
            src/main/jni/jthread/jmutex.cpp
            src/main/jni/jthread/jthread.cpp

            src/main/jni/JRTPLIB/src/rtcpapppacket.cpp
            src/main/jni/JRTPLIB/src/rtcpbyepacket.cpp
            src/main/jni/JRTPLIB/src/rtcpcompoundpacket.cpp
            src/main/jni/JRTPLIB/src/rtcpcompoundpacketbuilder.cpp
            src/main/jni/JRTPLIB/src/rtcppacket.cpp
            src/main/jni/JRTPLIB/src/rtcppacketbuilder.cpp
            src/main/jni/JRTPLIB/src/rtcprrpacket.cpp
            src/main/jni/JRTPLIB/src/rtcpscheduler.cpp
            src/main/jni/JRTPLIB/src/rtcpsdesinfo.cpp
            src/main/jni/JRTPLIB/src/rtcpsdespacket.cpp
            src/main/jni/JRTPLIB/src/rtcpsrpacket.cpp
            src/main/jni/JRTPLIB/src/rtpcollisionlist.cpp
            src/main/jni/JRTPLIB/src/rtpdebug.cpp
            src/main/jni/JRTPLIB/src/rtperrors.cpp
            src/main/jni/JRTPLIB/src/rtpinternalsourcedata.cpp
            src/main/jni/JRTPLIB/src/rtpipv4address.cpp
            src/main/jni/JRTPLIB/src/rtpipv6address.cpp
            src/main/jni/JRTPLIB/src/rtpipv4destination.cpp
            src/main/jni/JRTPLIB/src/rtpipv6destination.cpp
            src/main/jni/JRTPLIB/src/rtplibraryversion.cpp
            src/main/jni/JRTPLIB/src/rtppacket.cpp
            src/main/jni/JRTPLIB/src/rtppacketbuilder.cpp
            src/main/jni/JRTPLIB/src/rtppollthread.cpp
            src/main/jni/JRTPLIB/src/rtprandom.cpp
            src/main/jni/JRTPLIB/src/rtprandomrand48.cpp
            src/main/jni/JRTPLIB/src/rtprandomrands.cpp
            src/main/jni/JRTPLIB/src/rtprandomurandom.cpp
            src/main/jni/JRTPLIB/src/rtpsession.cpp
            src/main/jni/JRTPLIB/src/rtpsessionparams.cpp
            src/main/jni/JRTPLIB/src/rtpsessionsources.cpp
            src/main/jni/JRTPLIB/src/rtpsourcedata.cpp
            src/main/jni/JRTPLIB/src/rtpsources.cpp
            src/main/jni/JRTPLIB/src/rtptimeutilities.cpp
            src/main/jni/JRTPLIB/src/rtpudpv4transmitter.cpp
            src/main/jni/JRTPLIB/src/rtpudpv6transmitter.cpp
            src/main/jni/JRTPLIB/src/rtpbyteaddress.cpp
            src/main/jni/JRTPLIB/src/rtpexternaltransmitter.cpp
            src/main/jni/JRTPLIB/src/rtpsecuresession.cpp
            src/main/jni/JRTPLIB/src/rtpabortdescriptors.cpp
            src/main/jni/JRTPLIB/src/rtptcpaddress.cpp
            src/main/jni/JRTPLIB/src/rtptcptransmitter.cpp

            src/main/jni/Common/thread/linux/thread_pthread.c
            src/main/jni/Common/thread/linux/Semaphore_linux.c
            src/main/jni/Common/thread/linux/mutex_pthread.c
            src/main/jni/Common/circular_list.c
            src/main/jni/AnsyncDecoder/AnsyncDecoder.c
            src/main/jni/AnsyncDecoder/sps_pps.c
            src/main/jni/display/display.c
            src/main/jni/jrtplibutil_jni.cpp
           )


target_link_libraries(# Specifies the target library.
                        jrtplib

                        log z android m GLESv2
                        ${PROJECT_SOURCE_DIR}/src/main/jni/ffmpeg/libs/android/${ANDROID_ABI}/libavdevice.a
                        ${PROJECT_SOURCE_DIR}/src/main/jni/ffmpeg/libs/android/${ANDROID_ABI}/libavformat.a
                        ${PROJECT_SOURCE_DIR}/src/main/jni/ffmpeg/libs/android/${ANDROID_ABI}/libswscale.a
                        ${PROJECT_SOURCE_DIR}/src/main/jni/ffmpeg/libs/android/${ANDROID_ABI}/libavcodec.a
                        ${PROJECT_SOURCE_DIR}/src/main/jni/ffmpeg/libs/android/${ANDROID_ABI}/libswresample.a
                        ${PROJECT_SOURCE_DIR}/src/main/jni/ffmpeg/libs/android/${ANDROID_ABI}/libavfilter.a
                        ${PROJECT_SOURCE_DIR}/src/main/jni/ffmpeg/libs/android/${ANDROID_ABI}/libavutil.a
                     )

