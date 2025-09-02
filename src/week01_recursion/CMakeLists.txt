# Week 01 – Recursion
file(GLOB_RECURSE WEEK01_SOURCES CONFIGURE_DEPENDS *.cpp)

foreach(file ${WEEK01_SOURCES})
    add_week_exec(week01_recursion ${file})
endforeach()
