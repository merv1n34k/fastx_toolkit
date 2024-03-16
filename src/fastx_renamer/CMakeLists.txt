add_executable(fastx_renamer
    fastx_renamer.c
)

# Ensure the executable can find the libfastx headers
target_include_directories(fastx_renamer PRIVATE
    ${PROJECT_SOURCE_DIR}/src/libfastx
    ${PROJECT_BINARY_DIR}
)

# Link the executable against libfastx
target_link_libraries(fastx_renamer PRIVATE
    libfastx
)

install(TARGETS fastx_renamer
    RUNTIME DESTINATION bin
)
