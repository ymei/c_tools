
PROJECT(test)

ADD_EXECUTABLE(boost_thread boost_thread.cpp)
ADD_EXECUTABLE(endian endian.cpp)
# ADD_EXECUTABLE(spirit spirit.cpp)

ADD_EXECUTABLE(async_udp async_udp.cpp)
ADD_EXECUTABLE(ptr_container ptr_container.cpp)

add_executable(mmap mmap.cpp)

add_executable(boost_fs boost_fs.cpp)
#target_link_libraries( pwosali ivymike )
#SET(CMAKE_CXX_FLAGS "--std=c++0x -Wall")
#get_target_property( ivy_dir ivymike LOCATION )
#SET(CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} -Wall --std=c++0x -I${ivy_dir}")
target_link_libraries( boost_thread boost_thread-mt boost_system-mt pthread ivymike )
target_link_libraries( endian ivymike )
target_link_libraries( async_udp boost_thread-mt boost_system-mt pthread ) 
target_link_libraries( boost_fs boost_filesystem-mt )
SET(CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} -Wall -fopenmp")


# SET(CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} -Wall -std=c++0x")
#SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -static")

# SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -L/space2/c_tools/barrier -lstupid" )