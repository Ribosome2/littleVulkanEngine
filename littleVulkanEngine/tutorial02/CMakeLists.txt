SET(exeName Tutorial02)
ADD_EXECUTABLE(Tutorial02
        main.cpp
        first_app.cpp
        first_app.hpp
        lve_pipeline.cpp
        lve_pipeline.hpp
        lve_window.cpp
        lve_window.hpp
        )

TARGET_LINK_LIBRARIES(Tutorial02 glfw)