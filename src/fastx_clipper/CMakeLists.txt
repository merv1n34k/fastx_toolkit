add_executable(fastx_clipper
    fastx_clipper.cpp
)

# Ensure the executable can find the libfastx headers
target_include_directories(fastx_clipper PRIVATE
    ${PROJECT_SOURCE_DIR}/src/libfastx
    ${PROJECT_BINARY_DIR}
)

# Link the executable against libfastx
target_link_libraries(fastx_clipper PRIVATE
    libfastx
)
