IF (BUILD_EXAMPLES)
  ADD_EXECUTABLE( test_nonlinear_kalman test_nonlinear_kalman.cpp ../nonlinearanalyticconditionalgaussianmobile.cpp ../mobile_robot.cpp ) 

  TARGET_LINK_LIBRARIES( test_nonlinear_kalman orocos-bfl ${MATRIX_LIBS} ${RNG_LIBS}  ${GINAC_LIBS})

  INCLUDE_DIRECTORIES(${CMAKE_BINARY_DIR}/src/wrappers/matrix ${CMAKE_SOURCE_DIR}/src ${RNG_INCLUDE} ${MATRIX_INCLUDE})

  INSTALL(TARGETS test_nonlinear_kalman
          DESTINATION ${CMAKE_INSTALL_PREFIX}/bin/bfl 
          PERMISSIONS OWNER_READ OWNER_WRITE OWNER_EXECUTE GROUP_READ GROUP_EXECUTE WORLD_READ WORLD_EXECUTE)

ENDIF (BUILD_EXAMPLES)

