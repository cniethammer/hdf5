cmake_minimum_required (VERSION 3.18)
project (HDF5_TOOLS_SRC_MISC C)

# --------------------------------------------------------------------
# Add the misc executables
# --------------------------------------------------------------------
#-- Misc Executables
if (BUILD_STATIC_LIBS)
  add_executable (h5debug ${HDF5_TOOLS_SRC_MISC_SOURCE_DIR}/h5debug.c)
  target_include_directories (h5debug PRIVATE "${HDF5_TOOLS_ROOT_DIR}/lib;${HDF5_SRC_INCLUDE_DIRS};${HDF5_SRC_BINARY_DIR};$<$<BOOL:${HDF5_ENABLE_PARALLEL}>:${MPI_C_INCLUDE_DIRS}>")
  target_compile_options(h5debug PRIVATE "${HDF5_CMAKE_C_FLAGS}")
  TARGET_C_PROPERTIES (h5debug STATIC)
  target_link_libraries (h5debug PRIVATE ${HDF5_TOOLS_LIB_TARGET} ${HDF5_LIB_TARGET})
  set_target_properties (h5debug PROPERTIES FOLDER tools)
  set_global_variable (HDF5_UTILS_TO_EXPORT "${HDF5_UTILS_TO_EXPORT};h5debug")

  add_executable (h5repart ${HDF5_TOOLS_SRC_MISC_SOURCE_DIR}/h5repart.c)
  target_include_directories (h5repart PRIVATE "${HDF5_TOOLS_ROOT_DIR}/lib;${HDF5_SRC_INCLUDE_DIRS};${HDF5_SRC_BINARY_DIR};$<$<BOOL:${HDF5_ENABLE_PARALLEL}>:${MPI_C_INCLUDE_DIRS}>")
  target_compile_options(h5repart PRIVATE "${HDF5_CMAKE_C_FLAGS}")
  TARGET_C_PROPERTIES (h5repart STATIC)
  target_link_libraries (h5repart PRIVATE ${HDF5_TOOLS_LIB_TARGET} ${HDF5_LIB_TARGET})
  set_target_properties (h5repart PROPERTIES FOLDER tools)
  set_global_variable (HDF5_UTILS_TO_EXPORT "${HDF5_UTILS_TO_EXPORT};h5repart")

  add_executable (h5mkgrp ${HDF5_TOOLS_SRC_MISC_SOURCE_DIR}/h5mkgrp.c)
  target_include_directories (h5mkgrp PRIVATE "${HDF5_TOOLS_ROOT_DIR}/lib;${HDF5_SRC_INCLUDE_DIRS};${HDF5_SRC_BINARY_DIR};$<$<BOOL:${HDF5_ENABLE_PARALLEL}>:${MPI_C_INCLUDE_DIRS}>")
  target_compile_options(h5mkgrp PRIVATE "${HDF5_CMAKE_C_FLAGS}")
  TARGET_C_PROPERTIES (h5mkgrp STATIC)
  target_link_libraries (h5mkgrp PRIVATE ${HDF5_TOOLS_LIB_TARGET} ${HDF5_LIB_TARGET})
  set_target_properties (h5mkgrp PROPERTIES FOLDER tools)
  set_global_variable (HDF5_UTILS_TO_EXPORT "${HDF5_UTILS_TO_EXPORT};h5mkgrp")

  add_executable (h5clear ${HDF5_TOOLS_SRC_MISC_SOURCE_DIR}/h5clear.c)
  target_include_directories (h5clear PRIVATE "${HDF5_TOOLS_ROOT_DIR}/lib;${HDF5_SRC_INCLUDE_DIRS};${HDF5_SRC_BINARY_DIR};$<$<BOOL:${HDF5_ENABLE_PARALLEL}>:${MPI_C_INCLUDE_DIRS}>")
  target_compile_options(h5clear PRIVATE "${HDF5_CMAKE_C_FLAGS}")
  TARGET_C_PROPERTIES (h5clear STATIC)
  target_link_libraries (h5clear PRIVATE ${HDF5_TOOLS_LIB_TARGET} ${HDF5_LIB_TARGET})
  set_target_properties (h5clear PROPERTIES FOLDER tools)
  set_global_variable (HDF5_UTILS_TO_EXPORT "${HDF5_UTILS_TO_EXPORT};h5clear")

  add_executable (h5delete ${HDF5_TOOLS_SRC_MISC_SOURCE_DIR}/h5delete.c)
  target_include_directories (h5delete PRIVATE "${HDF5_TOOLS_ROOT_DIR}/lib;${HDF5_SRC_INCLUDE_DIRS};${HDF5_SRC_BINARY_DIR};$<$<BOOL:${HDF5_ENABLE_PARALLEL}>:${MPI_C_INCLUDE_DIRS}>")
  target_compile_options(h5delete PRIVATE "${HDF5_CMAKE_C_FLAGS}")
  TARGET_C_PROPERTIES (h5delete STATIC)
  target_link_libraries (h5delete PRIVATE ${HDF5_TOOLS_LIB_TARGET} ${HDF5_LIB_TARGET})
  set_target_properties (h5delete PROPERTIES FOLDER tools)
  set_global_variable (HDF5_UTILS_TO_EXPORT "${HDF5_UTILS_TO_EXPORT};h5delete")

  set (H5_DEP_EXECUTABLES
      h5debug
      h5repart
      h5mkgrp
      h5clear
      h5delete
  )
endif ()
if (BUILD_SHARED_LIBS)
  add_executable (h5debug-shared ${HDF5_TOOLS_SRC_MISC_SOURCE_DIR}/h5debug.c)
  target_include_directories (h5debug-shared PRIVATE "${HDF5_TOOLS_ROOT_DIR}/lib;${HDF5_SRC_INCLUDE_DIRS};${HDF5_SRC_BINARY_DIR};$<$<BOOL:${HDF5_ENABLE_PARALLEL}>:${MPI_C_INCLUDE_DIRS}>")
  TARGET_C_PROPERTIES (h5debug-shared SHARED)
  target_compile_options(h5debug-shared PRIVATE "${HDF5_CMAKE_C_FLAGS}")
  target_link_libraries (h5debug-shared PRIVATE ${HDF5_TOOLS_LIBSH_TARGET} ${HDF5_LIBSH_TARGET})
  set_target_properties (h5debug-shared PROPERTIES FOLDER tools)
  set_global_variable (HDF5_UTILS_TO_EXPORT "${HDF5_UTILS_TO_EXPORT};h5debug-shared")

  add_executable (h5repart-shared ${HDF5_TOOLS_SRC_MISC_SOURCE_DIR}/h5repart.c)
  target_include_directories (h5repart-shared PRIVATE "${HDF5_TOOLS_ROOT_DIR}/lib;${HDF5_SRC_INCLUDE_DIRS};${HDF5_SRC_BINARY_DIR};$<$<BOOL:${HDF5_ENABLE_PARALLEL}>:${MPI_C_INCLUDE_DIRS}>")
  target_compile_options(h5repart-shared PRIVATE "${HDF5_CMAKE_C_FLAGS}")
  TARGET_C_PROPERTIES (h5repart-shared SHARED)
  target_link_libraries (h5repart-shared PRIVATE ${HDF5_TOOLS_LIBSH_TARGET} ${HDF5_LIBSH_TARGET})
  set_target_properties (h5repart-shared PROPERTIES FOLDER tools)
  set_global_variable (HDF5_UTILS_TO_EXPORT "${HDF5_UTILS_TO_EXPORT};h5repart-shared")

  add_executable (h5mkgrp-shared ${HDF5_TOOLS_SRC_MISC_SOURCE_DIR}/h5mkgrp.c)
  target_include_directories (h5mkgrp-shared PRIVATE "${HDF5_TOOLS_ROOT_DIR}/lib;${HDF5_SRC_INCLUDE_DIRS};${HDF5_SRC_BINARY_DIR};$<$<BOOL:${HDF5_ENABLE_PARALLEL}>:${MPI_C_INCLUDE_DIRS}>")
  target_compile_options(h5mkgrp-shared PRIVATE "${HDF5_CMAKE_C_FLAGS}")
  TARGET_C_PROPERTIES (h5mkgrp-shared SHARED)
  target_link_libraries (h5mkgrp-shared PRIVATE ${HDF5_TOOLS_LIBSH_TARGET} ${HDF5_LIBSH_TARGET})
  set_target_properties (h5mkgrp-shared PROPERTIES FOLDER tools)
  set_global_variable (HDF5_UTILS_TO_EXPORT "${HDF5_UTILS_TO_EXPORT};h5mkgrp-shared")

  add_executable (h5clear-shared ${HDF5_TOOLS_SRC_MISC_SOURCE_DIR}/h5clear.c)
  target_include_directories (h5clear-shared PRIVATE "${HDF5_TOOLS_ROOT_DIR}/lib;${HDF5_SRC_INCLUDE_DIRS};${HDF5_SRC_BINARY_DIR};$<$<BOOL:${HDF5_ENABLE_PARALLEL}>:${MPI_C_INCLUDE_DIRS}>")
  target_compile_options(h5clear-shared PRIVATE "${HDF5_CMAKE_C_FLAGS}")
  TARGET_C_PROPERTIES (h5clear-shared SHARED)
  target_link_libraries (h5clear-shared PRIVATE ${HDF5_TOOLS_LIBSH_TARGET} ${HDF5_LIBSH_TARGET})
  set_target_properties (h5clear-shared PROPERTIES FOLDER tools)
  set_global_variable (HDF5_UTILS_TO_EXPORT "${HDF5_UTILS_TO_EXPORT};h5clear-shared")

  add_executable (h5delete-shared ${HDF5_TOOLS_SRC_MISC_SOURCE_DIR}/h5delete.c)
  target_include_directories (h5delete-shared PRIVATE "${HDF5_TOOLS_ROOT_DIR}/lib;${HDF5_SRC_INCLUDE_DIRS};${HDF5_SRC_BINARY_DIR};$<$<BOOL:${HDF5_ENABLE_PARALLEL}>:${MPI_C_INCLUDE_DIRS}>")
  target_compile_options(h5delete-shared PRIVATE "${HDF5_CMAKE_C_FLAGS}")
  TARGET_C_PROPERTIES (h5delete-shared SHARED)
  target_link_libraries (h5delete-shared PRIVATE ${HDF5_TOOLS_LIBSH_TARGET} ${HDF5_LIBSH_TARGET})
  set_target_properties (h5delete-shared PROPERTIES FOLDER tools)
  set_global_variable (HDF5_UTILS_TO_EXPORT "${HDF5_UTILS_TO_EXPORT};h5delete-shared")

  set (H5_DEP_EXECUTABLES ${H5_DEP_EXECUTABLES}
      h5debug-shared
      h5repart-shared
      h5mkgrp-shared
      h5clear-shared
      h5delete-shared
  )
endif ()

#-----------------------------------------------------------------------------
# Add Target to clang-format
#-----------------------------------------------------------------------------
if (HDF5_ENABLE_FORMATTERS)
  if (BUILD_STATIC_LIBS)
    clang_format (HDF5_H5DEBUG_SRC_FORMAT h5debug)
    clang_format (HDF5_H5REPART_SRC_FORMAT h5repart)
    clang_format (HDF5_H5MKGRP_SRC_FORMAT h5mkgrp)
    clang_format (HDF5_H5CLEAR_SRC_FORMAT h5clear)
    clang_format (HDF5_H5DELETE_SRC_FORMAT h5delete)
  else ()
    clang_format (HDF5_H5DEBUG_SRC_FORMAT h5debug-shared)
    clang_format (HDF5_H5REPART_SRC_FORMAT h5repart-shared)
    clang_format (HDF5_H5MKGRP_SRC_FORMAT h5mkgrp-shared)
    clang_format (HDF5_H5CLEAR_SRC_FORMAT h5clear-shared)
    clang_format (HDF5_H5DELETE_SRC_FORMAT h5delete-shared)
  endif ()
endif ()

##############################################################################
##############################################################################
###           I N S T A L L A T I O N                                      ###
##############################################################################
##############################################################################

#-----------------------------------------------------------------------------
# Rules for Installation of tools using make Install target
#-----------------------------------------------------------------------------
if (HDF5_EXPORTED_TARGETS)
  foreach (exec ${H5_DEP_EXECUTABLES})
    INSTALL_PROGRAM_PDB (${exec} ${HDF5_INSTALL_BIN_DIR} toolsapplications)
  endforeach ()

  install (
      TARGETS
          ${H5_DEP_EXECUTABLES}
      EXPORT
          ${HDF5_EXPORTED_TARGETS}
      RUNTIME DESTINATION ${HDF5_INSTALL_BIN_DIR} COMPONENT toolsapplications
  )
endif ()
