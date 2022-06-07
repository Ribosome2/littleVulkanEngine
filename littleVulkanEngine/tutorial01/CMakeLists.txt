ADD_EXECUTABLE(Tutorial01
        main.cpp
        lve_app_base.cpp
        lve_app_base.hpp
        lve_window.cpp
        lve_window.hpp
        )

TARGET_LINK_LIBRARIES(Tutorial01 glfw)