SET(EXE_NAME Tutorial05)
ADD_EXECUTABLE(${EXE_NAME}
        main.cpp
        first_app.cpp
        first_app.hpp
        lve_device.cpp
        lve_device.hpp
        lve_swap_chain.cpp
        lve_swap_chain.hpp
        lve_pipeline.cpp
        lve_pipeline.hpp
        lve_window.cpp
        lve_window.hpp
        )

#must specify link Vulkan::Vulkan here  or there will be unresolved linking error
TARGET_LINK_LIBRARIES(${EXE_NAME} glfw Vulkan::Vulkan)