add_executable(fasta_nucleotide_changer
    fasta_nucleotide_changer.c
)

# Ensure the executable can find the libfastx headers
target_include_directories(fasta_nucleotide_changer PRIVATE
    ${PROJECT_SOURCE_DIR}/src/libfastx
    ${PROJECT_BINARY_DIR}
)

# Link the executable against libfastx
target_link_libraries(fasta_nucleotide_changer PRIVATE
    libfastx
)

