set(MODULE_NAME ImGui)

file(GLOB_RECURSE ${MODULE_NAME}_SOURCE CONFIGURE_DEPENDS
    "${CMAKE_CURRENT_SOURCE_DIR}/source/*.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/include/*.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/include/*.hpp"
)

add_library(${MODULE_NAME} STATIC ${${MODULE_NAME}_SOURCE})

set_target_properties(${MODULE_NAME} PROPERTIES FOLDER "Engine")

source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${${MODULE_NAME}_SOURCE})

target_include_directories(${MODULE_NAME} PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)
