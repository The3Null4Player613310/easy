if (NOT TARGET fmt)
  add_library(fmt INTERFACE)
  target_include_directories(fmt INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/fmt)
  target_compile_definitions(fmt INTERFACE FMT_HEADER_ONLY)
endif()

if (NOT TARGET args)
  add_library(args INTERFACE)
  target_include_directories(args INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/args)
endif()

if (NOT TARGET json)
  add_library(json INTERFACE)
  target_include_directories(json INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/json/include)
endif()

if (NOT TARGET kitty)
  add_library(kitty INTERFACE)
  target_include_directories(kitty INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/kitty/include)
endif()

if (NOT TARGET rang)
  add_library(rang INTERFACE)
  target_include_directories(rang INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/rang)
endif()

if (NOT TARGET lorina)
  add_library(lorina INTERFACE)
  target_include_directories(lorina INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/lorina/include)
  target_link_libraries(lorina INTERFACE fmt rang)
endif()

if (NOT TARGET any)
  add_library(any INTERFACE)
  target_include_directories(any INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/any)
endif()

if (NOT TARGET cli11)
  add_library(cli11 INTERFACE) # v1.3
  target_include_directories(cli11 INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/cli11)
endif()

if (NOT TARGET alice)
  add_library(alice INTERFACE)
  target_include_directories(alice INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/alice/include)
  target_link_libraries(alice INTERFACE readline)
endif()

if (NOT TARGET glucose)
  add_library(glucose INTERFACE)
  target_include_directories(glucose INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/glucose/include)
endif()
