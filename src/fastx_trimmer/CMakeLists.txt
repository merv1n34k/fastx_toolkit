add_executable(fastx_trimmer
    fastx_trimmer.c
)

# Ensure the executable can find the libfastx headers
target_include_directories(fastx_trimmer PRIVATE
    ${PROJECT_SOURCE_DIR}/src/libfastx
    ${PROJECT_BINARY_DIR}
)

# Link the executable against libfastx
target_link_libraries(fastx_trimmer PRIVATE
    libfastx
)

install(TARGETS fastx_trimmer
    RUNTIME DESTINATION bin
)
