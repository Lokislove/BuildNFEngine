cmake_minimum_required(VERSION 2.8)

project(NoahFrame)
set(SolutionDir ${PROJECT_SOURCE_DIR})
# message(STATUS "SolutionDir=" ${SolutionDir})
include_directories(
${SolutionDir}
${SolutionDir}/Dependencies/ 
${SolutionDir}/Dependencies/Theron/Include/ 
${SolutionDir}/Dependencies/Theron/Include/External/
)

add_definitions(-std=c++11)

if(UNIX)
	set(CMAKE_CXX_FLAGS_DEBUG "$ENV{CXXFLAGS}  -std=c++11 -O0 -Wall -g -ggdb")
	set(CMAKE_CXX_FLAGS_RELEASE "$ENV{CXXFLAGS}  -std=c++11 -O3 -Wall")
	set(LDFLAGS "$ENV{LDFLAGS} -stdlib=libc++")
endif()
set(DependenciesLibPath ${SolutionDir}/Dependencies/lib)
link_directories(${DependenciesLibPath})
add_subdirectory(Dependencies)
add_subdirectory(NFComm)
