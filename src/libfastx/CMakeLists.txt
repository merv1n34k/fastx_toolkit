
# Define the libfastx static library
add_library(libfastx STATIC
    chomp.c
    fastx.c
    fastx_args.c
    sequence_alignment.cpp
    chomp.h
    fastx.h
    fastx_args.h
    sequence_alignment.h
)

target_include_directories(libfastx PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR} # Allows others to include libfastx headers
)

