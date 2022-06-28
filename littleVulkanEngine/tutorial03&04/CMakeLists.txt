SET(EXE_NAME Tutorial03And04)
ADD_EXECUTABLE(${EXE_NAME}
        main.cpp
        first_app.cpp
        first_app.hpp
        lve_device.cpp
        lve_device.hpp
        lve_pipeline.cpp
        lve_pipeline.hpp
        lve_window.cpp
        lve_window.hpp
        )

TARGET_LINK_LIBRARIES(${EXE_NAME} glfw)