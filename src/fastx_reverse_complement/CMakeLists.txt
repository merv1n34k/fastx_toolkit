add_executable(fastx_reverse_complement
    fastx_reverse_complement.c
)

# Ensure the executable can find the libfastx headers
target_include_directories(fastx_reverse_complement PRIVATE
    ${PROJECT_SOURCE_DIR}/src/libfastx
)

# Link the executable against libfastx
target_link_libraries(fastx_reverse_complement PRIVATE
    libfastx
)

