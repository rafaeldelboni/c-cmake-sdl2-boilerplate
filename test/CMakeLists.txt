# Config

# 1. Declare the test file
set(Tests
  runner
  runner2)

# 2. Declare dependencies of each test file
set(runner_deps
  example)

set(runner2_deps
  "")

# 3. Add dependencies to a list, need to be in the same order as item 1
set(Dependencies
  runner_deps
  runner2_deps)

###################################################################

foreach(tst deps IN ZIP_LISTS Tests Dependencies)
  message(STATUS "test=${tst}, dependencies=${deps}")
  add_executable(
    ${tst}
    ${tst}.c)

  target_link_libraries(
    ${tst}
    unity)

  foreach(dep ${${deps}})
    message(STATUS "-> test=${tst}, dependency=${dep}")
    target_link_libraries(
      ${tst}
      ${dep})
  endforeach(dep)

  target_include_directories(
    ${tst} PUBLIC
    ${PROJECT_SOURCE_DIR}/test/unity)

  set_target_properties(
    ${tst}
    PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${TEST_OUTPUT_PATH}")

  add_test(${tst} "${TEST_OUTPUT_PATH}/${tst}")
endforeach()
