cmake_minimum_required(VERSION 3.16)
project(MobileBloxV2)

set(CMAKE_CXX_STANDARD 17)

# Tìm tất cả file .cpp
file(GLOB_RECURSE SOURCES 
    "*.cpp"
)

# Tạo shared library
add_library(mobileblox SHARED ${SOURCES})

# Link với log library của Android
find_library(log-lib log)
target_link_libraries(mobileblox ${log-lib})
