install(DIRECTORY .
        DESTINATION include
        COMPONENT cxxabi-headers
        FILES_MATCHING
        PATTERN *
        PATTERN "CMakeLists.txt" EXCLUDE
        PERMISSIONS OWNER_READ OWNER_WRITE GROUP_READ WORLD_READ
        )
add_custom_target(install-cxxabi-headers
        COMMAND "${CMAKE_COMMAND}"
        -DCMAKE_INSTALL_COMPONENT=cxxabi-headers
        -P "${CMAKE_BINARY_DIR}/cmake_install.cmake")