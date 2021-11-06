# Copyright (C) 2017-2018 Jonathan Müller <jonathanmueller.dev@gmail.com>
# This file is subject to the license terms in the LICENSE file
# found in the top-level directory of this distribution.

function(_cppast_example name)
    set(target cppast_example_${name})
    add_executable(${target} ${name}.cpp example_parser.hpp)
    target_link_libraries(${target} PUBLIC cppast)
    install(TARGETS ${target} EXPORT cppastTargets
      RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR})
endfunction()

_cppast_example(ast_printer)
_cppast_example(comparison)
_cppast_example(documentation_generator)
_cppast_example(enum_category)
_cppast_example(enum_to_string)
_cppast_example(serialization)
