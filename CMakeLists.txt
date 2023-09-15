cmake_minimum_required(VERSION 3.25)
project(nonuniquefilenamesbuild)

add_compile_options(/MP)

set(nonunique_sources "")
set(unique_sources "")

foreach(i RANGE 50)
  configure_file(source.in.cpp ${i}/source.cpp)
  list(APPEND nonunique_sources ${i}/source.cpp)
  configure_file(source.in.cpp ${i}/source-${i}.cpp)
  list(APPEND unique_sources ${i}/source-${i}.cpp)
endforeach()

add_executable(nonunique main.cpp ${nonunique_sources})
add_executable(unique main.cpp ${unique_sources})
