add_executable(fastq_masker
    fastq_masker.c
)

# Ensure the executable can find the libfastx headers
target_include_directories(fastq_masker PRIVATE
    ${PROJECT_SOURCE_DIR}/src/libfastx
    ${PROJECT_BINARY_DIR}
)

# Link the executable against libfastx
target_link_libraries(fastq_masker PRIVATE
    libfastx
)
