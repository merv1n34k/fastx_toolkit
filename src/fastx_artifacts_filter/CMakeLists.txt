add_executable(fastx_artifacts_filter
    fastx_artifacts_filter.c
)

# Ensure the executable can find the libfastx headers
target_include_directories(fastx_artifacts_filter PRIVATE
    ${PROJECT_SOURCE_DIR}/src/libfastx
)

# Link the executable against libfastx
target_link_libraries(fastx_artifacts_filter PRIVATE
    libfastx
)
