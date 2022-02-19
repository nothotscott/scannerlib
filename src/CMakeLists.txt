
list(APPEND SOURCE
    scannerlib.c)

add_library(scannerlib_object OBJECT ${SOURCE})
target_link_libraries(scannerlib_object liquid)

add_library(scannerlib SHARED)
target_link_libraries(scannerlib scannerlib_object)

add_library(scannerlib_static STATIC)
target_link_libraries(scannerlib_static scannerlib_object)
SET_TARGET_PROPERTIES(scannerlib_static PROPERTIES OUTPUT_NAME "scannerlib")
