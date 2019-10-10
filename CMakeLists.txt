add_contract(bomb bomb ${CMAKE_CURRENT_SOURCE_DIR}/src/bomb.cpp)

target_include_directories(bomb
   PUBLIC
   ${CMAKE_CURRENT_SOURCE_DIR}/include)

set_target_properties(bomb
   PROPERTIES
   RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}")

configure_file( ${CMAKE_CURRENT_SOURCE_DIR}/ricardian/bomb.contracts.md.in ${CMAKE_CURRENT_BINARY_DIR}/ricardian/bomb.contracts.md @ONLY )

target_compile_options( bomb PUBLIC -R${CMAKE_CURRENT_SOURCE_DIR}/ricardian -R${CMAKE_CURRENT_BINARY_DIR}/ricardian )
