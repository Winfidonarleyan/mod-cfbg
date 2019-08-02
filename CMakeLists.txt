#
# Copyright (С) since 2019 Andrei Guluaev (Winfidonarleyan/Kargatum) https://github.com/Winfidonarleyan 
# Licence MIT https://opensource.org/MIT
#

# Add cpp files
if(NOT KARGATUMCORE)
  AC_ADD_SCRIPT("${CMAKE_CURRENT_LIST_DIR}/src/CFBG.cpp")
  AC_ADD_SCRIPT("${CMAKE_CURRENT_LIST_DIR}/src/CFBG_SC.cpp")
  AC_ADD_SCRIPT("${CMAKE_CURRENT_LIST_DIR}/src/CFBG.h")
endif()

# Add scripts to script loader
AC_ADD_SCRIPT_LOADER("CFBG" "${CMAKE_CURRENT_LIST_DIR}/src/CFBGLoad.h")

# Add config file
if (NOT KARGATUMCORE)
  AC_ADD_CONFIG_FILE("${CMAKE_CURRENT_LIST_DIR}/conf/CFBG.conf.dist")
endif()
