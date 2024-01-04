cmake_minimum_required(VERSION 3.28)

project(postgres_demo LANGUAGES C)

set(PostgreSQL_INCLUDE_DIR "/usr/local/include/postgresql@14")
set(PostgreSQL_LIBRARY_DIR "/usr/local/lib/postgresql@14")

find_package(PostgreSQL 14.10 REQUIRED)

add_executable(testlibpq testlibpq.c)
target_link_libraries(testlibpq PostgreSQL::PostgreSQL)

message("Is PostgreSQL found in the system: ${PostgreSQL_FOUND}")
message("The include directories of PostgreSQL: ${PostgreSQL_INCLUDE_DIRS}")
message("The link directories of PostgreSQL: ${PostgreSQL_LIBRARY_DIRS}")
message("The PostgreSQL libraries: ${PostgreSQL_LIBRARIES}")
