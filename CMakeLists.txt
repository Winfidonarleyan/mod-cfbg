#
# Copyright (С) since 2019 Andrei Guluaev (Winfidonarleyan/Kargatum) https://github.com/Winfidonarleyan 
# Licence MIT https://opensource.org/MIT
#

# Set global dir
CU_SET_PATH("KARGATUM_CFBG_DIR" "${CMAKE_CURRENT_LIST_DIR}")

# Loading system
CU_ADD_HOOK(AFTER_LOAD_CMAKE_MODULES "${CMAKE_CURRENT_LIST_DIR}/cmake/LoadSystem.cmake")

# Add includes in game lib
CU_ADD_HOOK(AFTER_GAME_LIBRARY "${CMAKE_CURRENT_LIST_DIR}/cmake/TargetInclude.cmake")

# Add cpp files
if(NOT KARGATUMCORE)
  AC_ADD_SCRIPT("${CMAKE_CURRENT_LIST_DIR}/src/KargatumCFBG.cpp")
  AC_ADD_SCRIPT("${CMAKE_CURRENT_LIST_DIR}/src/KargatumCFBG.h")
endif()

# Add scripts to script loader
AC_ADD_SCRIPT_LOADER("KargatumCFBG" "${CMAKE_CURRENT_LIST_DIR}/src/KargatumCFBGLoad.h")

# Add config file
if (NOT KARGATUMCORE)
  AC_ADD_CONFIG_FILE("${CMAKE_CURRENT_LIST_DIR}/conf/KargatumCFBG.conf.dist")
endif()
