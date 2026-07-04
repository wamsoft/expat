# expat プラグイン
#   expat (XML パーサ) を使用。vcpkg の expat を参照する。

# スタンドアロン configure も可能にするため TPSTUB_DIR を既定補完する
if(NOT DEFINED TPSTUB_DIR)
    set(TPSTUB_DIR ${CMAKE_CURRENT_SOURCE_DIR}/../tp_stub CACHE PATH "Path to tp_stub directory")
endif()
include(${TPSTUB_DIR}/krkrz.cmake)

find_package(expat CONFIG REQUIRED)

krkrz_plugin(expat
    NCBIND
    SOURCES
        Main.cpp
    INCLUDES
        ${CMAKE_CURRENT_SOURCE_DIR}
    LIBRARIES
        expat::expat
)
