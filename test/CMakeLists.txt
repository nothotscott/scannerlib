
function(bundle_test name _sources)
    add_executable(${name} ${_sources})
    target_link_libraries(${name} PRIVATE scannerlib)
    add_test(NAME ${name} COMMAND ${name})
endfunction()

bundle_test(test1 test1.c)
