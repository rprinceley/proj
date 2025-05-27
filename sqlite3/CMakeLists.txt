set(SRC_SQLITE
  sqlite3.c
  shell.c)

add_executable(sqlite3 ${SRC_SQLITE})
if (NOT WIN32)
  find_library(MATH_LIBRARY m)
  if(MATH_LIBRARY)
    target_link_libraries(sqlite3 PRIVATE ${MATH_LIBRARY})
  endif()
endif()
