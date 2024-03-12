add_executable(fastx_collapser
    fastx_collapser.cpp
    std_hash.h
)

# Ensure the executable can find the libfastx headers
target_include_directories(fastx_collapser PRIVATE
    ${PROJECT_SOURCE_DIR}/src/libfastx
)

# Link the executable against libfastx
target_link_libraries(fastx_collapser PRIVATE
    libfastx
)
