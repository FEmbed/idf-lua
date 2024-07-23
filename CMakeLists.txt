idf_build_get_property(components_to_build BUILD_COMPONENTS)

set(src)
set(include)
set(priv_requires)

FILE(GLOB srcs       
        "src/lapi.c"
        "src/lcode.c"
        "src/lctype.c"
        "src/ldebug.c"
        "src/ldo.c"
        "src/ldump.c"
        "src/lfunc.c"
        "src/lgc.c"
        "src/llex.c"
        "src/lmem.c"
        "src/lobject.c"
        "src/lopcodes.c"
        "src/lparser.c"
        "src/lstate.c"
        "src/lstring.c"
        "src/ltable.c"
        "src/ltm.c"
        "src/lundump.c"
        "src/lvm.c"
        "src/lzio.c"
        "src/ltests.c"
        "src/lauxlib.c"
        "src/lbaselib.c"
        "src/ldblib.c"
        "src/liolib.c"
        "src/lmathlib.c"
        "src/loslib.c"
        "src/ltablib.c"
        "src/lstrlib.c"
        "src/lutf8lib.c"
        "src/loadlib.c"
        "src/lcorolib.c"
        "src/linit.c"
)

set(include "include" "src")

idf_component_register(SRCS "${srcs}"
        INCLUDE_DIRS ${include}
        REQUIRES "FEmbed-Arduino FEmbed-OS"
        PRIV_REQUIRES ${priv_requires})

target_compile_definitions(${COMPONENT_LIB} PRIVATE -DARDUINO_ARCH_ESP32)