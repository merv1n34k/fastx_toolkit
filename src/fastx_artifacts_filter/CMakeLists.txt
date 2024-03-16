add_executable(fastx_artifacts_filter
    fastx_artifacts_filter.c
)

# Ensure the executable can find the libfastx headers
target_include_directories(fastx_artifacts_filter PRIVATE
    ${PROJECT_SOURCE_DIR}/src/libfastx
    ${PROJECT_BINARY_DIR}
)

# Link the executable against libfastx
target_link_libraries(fastx_artifacts_filter PRIVATE
    libfastx
)

install(TARGETS fastx_artifacts_filter
    RUNTIME DESTINATION bin
)
