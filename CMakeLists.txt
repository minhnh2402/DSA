cmake_minimum_required(VERSION 3.20)
project(dsa_embedded LANGUAGES CXX)

# ─── Options ────────────────────────────────────────────────
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Output dir
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

# Include common headers
include_directories(${CMAKE_SOURCE_DIR}/include)

# ─── Function to add a weekly executable ────────────────────
function(add_week_exec week_name source_file)
    get_filename_component(target_name ${source_file} NAME_WE)
    add_executable(${week_name}_${target_name} ${source_file})
    set_target_properties(${week_name}_${target_name} PROPERTIES
        RUNTIME_OUTPUT_DIRECTORY ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/${week_name}
    )
endfunction()

# ─── Add each week as subdirectory ──────────────────────────
add_subdirectory(src/week01_recursion)
# add_subdirectory(src/week02_array)
# add_subdirectory(src/week03_strings)
# add_subdirectory(src/week04_linked_list)
# add_subdirectory(src/week05_stack_queue)
# add_subdirectory(src/week06_trees)
# add_subdirectory(src/week07_binary_search_bit)
# add_subdirectory(src/week08_sorting)
# add_subdirectory(src/week09_hashing_prefixsum)
# add_subdirectory(src/week10_heap)
# add_subdirectory(src/week11_graphs)
# add_subdirectory(src/week12_dp)
