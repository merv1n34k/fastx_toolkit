add_executable(seqalign_test
    seqalign_test.cpp
)

# Ensure the executable can find the libfastx headers
target_include_directories(seqalign_test PRIVATE
    ${PROJECT_SOURCE_DIR}/src/libfastx
)

# Link the executable against libfastx
target_link_libraries(seqalign_test PRIVATE
    libfastx
)

