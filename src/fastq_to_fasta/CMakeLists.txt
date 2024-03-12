add_executable(fastq_to_fasta
    fastq_to_fasta.c
)

# Ensure the executable can find the libfastx headers
target_include_directories(fastq_to_fasta PRIVATE
    ${PROJECT_SOURCE_DIR}/src/libfastx
)

# Link the executable against libfastx
target_link_libraries(fastq_to_fasta PRIVATE
    libfastx
)

