file(TO_CMAKE_PATH "${CMAKE_INSTALL_PREFIX}"
  ROBOTLOCOMOTION-LCMTYPES_INSTALL_PREFIX)

configure_file(${PROJECT_NAME}.pc.in
  ${PROJECT_BINARY_DIR}/${PROJECT_NAME}.pc @ONLY)
install(FILES ${PROJECT_BINARY_DIR}/${PROJECT_NAME}.pc
  DESTINATION lib${LIB_SUFFIX}/pkgconfig)

if(TARGET robotlocomotion-lcmtypes-jar)
  configure_file(${PROJECT_NAME}-java.pc.in
    ${PROJECT_BINARY_DIR}/${PROJECT_NAME}-java.pc @ONLY)
  install(FILES ${PROJECT_BINARY_DIR}/${PROJECT_NAME}-java.pc
    DESTINATION lib${LIB_SUFFIX}/pkgconfig)
endif()
