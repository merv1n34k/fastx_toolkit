add_executable(fastx_quality_stats
    fastx_quality_stats.c
)

# Ensure the executable can find the libfastx headers
target_include_directories(fastx_quality_stats PRIVATE
    ${PROJECT_SOURCE_DIR}/src/libfastx
    ${PROJECT_BINARY_DIR}
)

# Link the executable against libfastx
target_link_libraries(fastx_quality_stats PRIVATE
    libfastx
)

install(TARGETS fastx_quality_stats
    RUNTIME DESTINATION bin
)
