

#-----------------------------------------------------------------
# CMake file for the MRPT application:  icp-slam
#
#  Run with "cmake ." at the root directory
#
#  October 2007, Jose Luis Blanco <jlblanco@ctima.uma.es>
#-----------------------------------------------------------------
project(icp-slam)

# ---------------------------------------------
# TARGET:
# ---------------------------------------------
# Define the executable target:
add_executable(${PROJECT_NAME}
               icp-slam_main.cpp
			    ${MRPT_VERSION_RC_FILE})

# Add the required libraries for linking:
target_link_libraries(${PROJECT_NAME} ${MRPT_LINKER_LIBS})

# Dependencies on MRPT libraries:
#  Just mention the top-level dependency, the rest will be detected automatically,
#  and all the needed #include<> dirs added (see the script DeclareAppDependencies.cmake for further details)
DeclareAppDependencies(${PROJECT_NAME} mrpt::apps)

DeclareAppForInstall(${PROJECT_NAME})
