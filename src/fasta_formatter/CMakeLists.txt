add_executable(fasta_formatter
    fasta_formatter.cpp
)

# Ensure the executable can find the libfastx headers
target_include_directories(fasta_formatter PRIVATE
    ${PROJECT_SOURCE_DIR}/src/libfastx
    ${PROJECT_BINARY_DIR}
)

# Link the executable against libfastx
target_link_libraries(fasta_formatter PRIVATE
    libfastx
    libgtextutils
)

install(TARGETS fasta_formatter
    RUNTIME DESTINATION bin
)

