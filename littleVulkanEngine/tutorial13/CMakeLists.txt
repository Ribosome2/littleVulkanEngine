SET(EXE_NAME Tutorial13_3DTransform-Perspective)
ADD_EXECUTABLE(${EXE_NAME}
        main.cpp
        first_app.cpp
        first_app.hpp
        lve_device.cpp
        lve_device.hpp
        lve_model.cpp
        lve_model.hpp
        lve_swap_chain.cpp
        lve_swap_chain.hpp
        lve_pipeline.cpp
        lve_pipeline.hpp
        lve_window.cpp
        lve_window.hpp
        lve_game_object.hpp
        lve_renderer.cpp
        lve_renderer.hpp
        simple_render_system.cpp
        simple_render_system.hpp
        lve_camera.cpp
        lve_camera.hpp
        )

#must specify link Vulkan::Vulkan here  or there will be unresolved linking error
TARGET_LINK_LIBRARIES(${EXE_NAME} glfw Vulkan::Vulkan)

#automatically build the shaders to spv
SET(SHADER_DIR ${CMAKE_CURRENT_SOURCE_DIR}/shaders)
MESSAGE("shaders directory: ${SHADER_DIR}")
ADD_CUSTOM_COMMAND(TARGET ${EXE_NAME} POST_BUILD
        COMMAND glslc ${SHADER_DIR}/simple_shader.vert -o ${SHADER_DIR}/simple_shader.vert.spv
        COMMAND glslc ${SHADER_DIR}/simple_shader.frag -o ${SHADER_DIR}/simple_shader.frag.spv
        )
