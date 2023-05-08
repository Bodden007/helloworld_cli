cmake_minimum_required (VERSION 3.26)

set(PROJECT_VESRION 0.1.${PATCH_VERSION})

project (helloworld_cli VERSION ${PROJECT_VESRION})
add_executable (helloworld_cli main.cpp)

set_target_properties(
	helloworld_cli PROPERTIES
	CXX_STANDARD 20
	CXX_STANDARD_REQUIRED ON
)

install(TARGETS helloworld_cli RUNTIME DESTINATION bin)

set(CPACK_GENERATOR DEB)

set(CPACK_PACKAGE_VERSION_MAJOR "${PROJECT_VERSION_MAJOR}")
set(CPACK_PACKAGE_VERSION_MINOR "${PROJECT_VERSION_MINOR}")
set(CPACK_PACKAGE_VERSION_PATCH "${PROJECT_VERSION_PATCH}")

set(CPACK_PACKAGE_CONTACT example@example.com)

include(CPack)

enable_testing()

add_test(test_cpp helloworld_cli)
