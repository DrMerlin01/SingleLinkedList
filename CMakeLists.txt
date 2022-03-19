cmake_minimum_required(VERSION 3.10)

project(SingleLinkedList)

set(CMAKE_CXX_STANDARD 17)

if(CMAKE_SYSTEM_NAME MATCHES "^MINGW")
    set(SYSTEM_LIBS -lstdc++)
else ()
    set(SYSTEM_LIBS)
endif()

set(INCLUDE_DIR inc)
set(SOURCE_DIR src)

set(FILES_SINGLE_LIST "${INCLUDE_DIR}/SingleLinkedList.h")
set(FILES_TESTS "${INCLUDE_DIR}/tests.h" "${SOURCE_DIR}/tests.cpp")
set(FILES_MAIN "${SOURCE_DIR}/main.cpp")

source_group("SingleLinkedList" FILES ${FILES_SINGLE_LIST})
source_group("Tests" FILES ${FILES_TESTS})
source_group("Source" FILES ${FILES_MAIN})

add_executable("list" ${FILES_MAIN} ${FILES_TESTS} ${FILES_SINGLE_LIST})
target_link_libraries("list" ${SYSTEM_LIBS})
