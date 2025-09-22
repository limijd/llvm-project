if(NOT TARGET libclang)
  message(STATUS "Skipping LibClangToyCompiler example because libclang is not available.")
  return()
endif()

add_llvm_example(LibClangToyCompiler ToyCompiler.cpp)

target_link_libraries(LibClangToyCompiler PRIVATE libclang)

target_include_directories(LibClangToyCompiler PRIVATE
  ${CLANG_SOURCE_DIR}/include
  ${CLANG_BINARY_DIR}/include
)

target_compile_features(LibClangToyCompiler PRIVATE cxx_std_17)
