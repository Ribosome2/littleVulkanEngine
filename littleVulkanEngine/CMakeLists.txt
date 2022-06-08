cmake_minimum_required(VERSION 3.21)
PROJECT(SimpleEngine)

FIND_PACKAGE(Vulkan REQUIRED)

INCLUDE_DIRECTORIES($ENV{VULKAN_SDK}/include)

INCLUDE_DIRECTORIES("third_party/glfw/src")

INCLUDE_DIRECTORIES("third_party/glfw/include" "third_party/glm")
LINK_DIRECTORIES("third_party/glfw")

ADD_SUBDIRECTORY(tutorial01)
ADD_SUBDIRECTORY(tutorial02)
ADD_SUBDIRECTORY(tutorial03&04)
ADD_SUBDIRECTORY(tutorial05)
ADD_SUBDIRECTORY(tutorial06)
ADD_SUBDIRECTORY(tutorial07)

