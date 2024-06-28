cmake_minimum_required(VERSION 3.5)
project(tiago_2dnav)

find_package(ament_cmake_auto REQUIRED)
ament_auto_find_build_dependencies()

if(pal_module_cmake_FOUND)
  pal_register_modules(module/20_localization.yaml
                      module/20_localization_w_composition.yaml
                      module/20_navigation.yaml
                      module/20_navigation_w_composition.yaml
                      module/20_slam.yaml)
endif()

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  ament_lint_auto_find_test_dependencies()
endif()

ament_auto_package(INSTALL_TO_SHARE config launch params)
