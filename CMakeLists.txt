cmake_minimum_required(VERSION 3.29)

project(cube_empty LANGUAGES CXX RC)

include(FetchContent)

FetchContent_Declare(
    D2RLPlugin
    GIT_REPOSITORY https://github.com/D2RLoader/PluginSDK.git
    GIT_TAG master
)

FetchContent_MakeAvailable(D2RLPlugin)

add_library(d2rl-cube-empty SHARED
    plugin.cpp
    plugin.rc
)

target_compile_features(d2rl-cube-empty PRIVATE cxx_std_20)

target_link_libraries(
    d2rl-cube-empty
    PRIVATE D2RLPlugin::D2RLPlugin
)

d2rlplugin_embed_config(
    TARGET d2rl-cube-empty
    FILE "${CMAKE_CURRENT_SOURCE_DIR}/cube-empty.toml"
)

set_target_properties(d2rl-cube-empty PROPERTIES
    OUTPUT_NAME "d2rl-cube-empty"
)
