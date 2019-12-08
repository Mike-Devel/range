# Copyright 2019 Mike Dev (mike.dev@gmx.de)
# Distributed under the Boost Software License, Version 1.0.
# See accompanying file LICENSE_1_0.txt or copy at http://www.boost.org/LICENSE_1_0.txt

cmake_minimum_required(VERSION 3.5)
project(BoostRange)

add_library(boost_range INTERFACE)
add_library(Boost::range ALIAS boost_range)

target_include_directories(boost_range INTERFACE include)

target_link_libraries(boost_range
    INTERFACE
        Boost::array
        Boost::assert
        Boost::concept_check
        Boost::config
        Boost::container_hash
        Boost::core
        Boost::detail
        Boost::iterator
        Boost::mpl
        Boost::numeric_conversion
        Boost::optional
        Boost::preprocessor
        Boost::regex
        Boost::static_assert
        Boost::tuple
        Boost::type_traits
        Boost::utility
)

add_executable(test_boost_range test/adaptor_test/tokenized.cpp)
target_link_libraries(test_boost_range PUBLIC Boost::range)