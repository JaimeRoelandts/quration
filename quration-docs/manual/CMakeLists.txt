cmake_minimum_required(VERSION 3.14)
project(QurationDocs NONE)

find_program(PANDOC_EXECUTABLE pandoc REQUIRED)

set(DOC_OUTPUT_DIR "${CMAKE_CURRENT_SOURCE_DIR}/man/man1")
file(MAKE_DIRECTORY ${DOC_OUTPUT_DIR})

file(GLOB_RECURSE MARKDOWN_FILES "**/*.md")

set(ALL_MAN_OUTPUTS "")

file(READ "${CMAKE_CURRENT_SOURCE_DIR}/../../Version.txt" PACKAGE_VERSION)
string(STRIP "${PACKAGE_VERSION}" PACKAGE_VERSION)

foreach(MD_FILE ${MARKDOWN_FILES})
  file (RELATIVE_PATH REL_MD ${CMAKE_CURRENT_SOURCE_DIR} ${MD_FILE})

  string(REGEX REPLACE "\\.md$" ".1" MAN_FILE ${REL_MD})
  set(OUTPUT_MAN "${DOC_OUTPUT_DIR}/${MAN_FILE}")

  get_filename_component(OUTPUT_SUBDIR ${OUTPUT_MAN} DIRECTORY)
  file(MAKE_DIRECTORY ${OUTPUT_SUBDIR})

  get_filename_component(FILE_NAME ${MD_FILE} NAME_WE)
  string(TOUPPER ${FILE_NAME} MAN_TITLE)

  add_custom_command(
    OUTPUT ${OUTPUT_MAN}
    COMMAND ${PANDOC_EXECUTABLE} "${MD_FILE}"
            -s
            -t man
            -M "title=${MAN_TITLE}"
            -M "section=1"
            -M "header=Quration User Manual"
            -M "footer=Version ${PACKAGE_VERSION}"
            -o "${OUTPUT_MAN}"
    DEPENDS "${MD_FILE}"
    COMMENT "Generating man page from ${MAN_TITLE}"
  )

  list(APPEND ALL_MAN_OUTPUTS ${OUTPUT_MAN})
endforeach()

add_custom_target(docs ALL DEPENDS ${ALL_MAN_OUTPUTS})

set_directory_properties(
  PROPERTIES ADDITIONAL_CLEAN_FILES "${CMAKE_CURRENT_SOURCE_DIR}/man"
)
