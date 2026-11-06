cmake_minimum_required(VERSION 3.28)
project(Lab LANGUAGES CXX)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

include(FetchContent)
FetchContent_Declare(SFML
    GIT_REPOSITORY https://github.com/SFML/SFML.git
    GIT_TAG 2.5.1
    GIT_SHALLOW ON
    EXCLUDE_FROM_ALL
    SYSTEM)
FetchContent_MakeAvailable(SFML)

add_executable(Lab) 
target_sources(Lab                                                                                        
    PRIVATE                                                                                               
        src/main.cpp                                                                                      
)
target_compile_features(Lab PRIVATE cxx_std_17)                                                           
target_link_libraries(Lab PRIVATE sfml-graphics) 

set_property(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT Lab)
