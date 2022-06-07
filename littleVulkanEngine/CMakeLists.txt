cmake_minimum_required(VERSION 3.21)
PROJECT(SimpleEngine)

FIND_PACKAGE(Vulkan REQUIRED)

INCLUDE_DIRECTORIES($ENV{VULKAN_SDK}/include)

INCLUDE_DIRECTORIES("third_party/glfw/src")

INCLUDE_DIRECTORIES("third_party/glfw/include")

ADD_SUBDIRECTORY(tutorial01)
ADD_SUBDIRECTORY(tutorial02)

