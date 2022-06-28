CMAKE_MINIMUM_REQUIRED(VERSION 3.21)
PROJECT(SimpleEngine)

FIND_PACKAGE(Vulkan REQUIRED)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

INCLUDE_DIRECTORIES($ENV{VULKAN_SDK}/include
        "../src"
        "../littleVulkanEngine/third_party/glm")

INCLUDE_DIRECTORIES("../littleVulkanEngine/third_party/glfw/src")

INCLUDE_DIRECTORIES("../littleVulkanEngine/third_party/glfw/include"
        "../littleVulkanEngine/third_party/glm"
        "../littleVulkanEngine/third_party/tiny_obj_loader")
LINK_DIRECTORIES("../littleVulkanEngine/third_party/glfw")

SET(EXE_NAME "LVE_ENGINE")
ADD_EXECUTABLE(${EXE_NAME}
        main.cpp
        first_app.hpp
        first_app.cpp
        keyboard_movement_controller.hpp
        keyboard_movement_controller.cpp
        lve_buffer.cpp
        lve_buffer.hpp
        lve_camera.hpp
        lve_camera.cpp
        lve_descriptors.hpp
        lve_descriptors.cpp
        lve_device.hpp
        lve_device.cpp
        lve_frame_info.hpp
        lve_game_object.hpp
        lve_game_object.cpp
        lve_model.hpp
        lve_model.cpp
        lve_pipeline.hpp
        lve_pipeline.cpp
        lve_renderer.hpp
        lve_renderer.cpp
        lve_swap_chain.hpp
        lve_swap_chain.cpp
        lve_utils.hpp
        lve_window.hpp
        lve_window.cpp

        lve_window.cpp
        lve_window.hpp
        systems/point_light_system.hpp
        systems/point_light_system.cpp
        systems/simple_render_system.hpp
        systems/simple_render_system.cpp

        )

TARGET_LINK_LIBRARIES(${EXE_NAME} glfw Vulkan::Vulkan)


SET(SHADER_DIR ${CMAKE_CURRENT_SOURCE_DIR}/../shaders)
MESSAGE("shaders directory: ${SHADER_DIR}")
ADD_CUSTOM_COMMAND(TARGET ${EXE_NAME} POST_BUILD
        COMMAND glslc ${SHADER_DIR}/simple_shader.vert -o ${SHADER_DIR}/simple_shader.vert.spv
        COMMAND glslc ${SHADER_DIR}/simple_shader.frag -o ${SHADER_DIR}/simple_shader.frag.spv
        COMMAND glslc ${SHADER_DIR}/point_light.vert -o ${SHADER_DIR}/point_light.vert.spv
        COMMAND glslc ${SHADER_DIR}/point_light.frag -o ${SHADER_DIR}/point_light.frag.spv
        )

