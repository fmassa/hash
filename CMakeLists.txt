cmake_minimum_required (VERSION 2.8)

find_package(Torch REQUIRED)

set(src
  hash.c
  fnv.c
  lookup.c
  murmur.c
)

set(luasrc
  init.lua
)

add_torch_package(hash "${src}" "${luasrc}" "Hash")

target_link_libraries(hash luaT TH)
