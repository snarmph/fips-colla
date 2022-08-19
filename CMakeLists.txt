#
# project: fips-colla
#

fips_begin_lib(colla)
    fips_dir(colla/src)
    fips_files(
        collatypes.h
        vec.h
        win32_slim.h 
        tracelog.h    tracelog.c
        str.h         str.c
        hashmap.h     hashmap.c
        utf8.h        utf8.c
        ini.h         ini.c
        strstream.h   strstream.c
        os.h          os.c
        file.h        file.c
        dir.h         dir.c
        socket.h      socket.c
        http.h        http.c
        cthreads.h    cthreads.c
    )
fips_end_lib()

if (FIPS_WINDOWS)
    target_link_libraries(colla ws2_32.lib)
else()
        target_link_libraries(colla pthread)
endif()

target_include_directories(colla PUBLIC colla/src)
