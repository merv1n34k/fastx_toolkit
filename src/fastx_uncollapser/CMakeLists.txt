add_executable(fastx_uncollapser fastx_uncollapser.cpp)

# Ensure the executable can find the libfastx headers
target_include_directories(fastx_uncollapser PRIVATE
    ${PROJECT_SOURCE_DIR}/src/libfastx
    ${PROJECT_BINARY_DIR}
)

# Link the executable against libfastx
target_link_libraries(fastx_uncollapser PRIVATE
    libfastx
    libgtextutils
)

