add_executable(fastq_quality_filter
    fastq_quality_filter.c
)

# Ensure the executable can find the libfastx headers
target_include_directories(fastq_quality_filter PRIVATE
    ${PROJECT_SOURCE_DIR}/src/libfastx
    ${PROJECT_BINARY_DIR}
)

# Link the executable against libfastx
target_link_libraries(fastq_quality_filter PRIVATE
    libfastx
)


