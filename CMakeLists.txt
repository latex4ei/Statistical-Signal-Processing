cmake_minimum_required(VERSION 2.8)

project(FS NONE)
include(UseLATEX)

add_custom_target(
	writegitid ALL
	COMMAND ${CMAKE_CURRENT_SOURCE_DIR}/write-gitid.sh
	WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
)

set(DRAWINGS
)

set(IMAGES
	img/Logo.pdf
	img/channel.pdf
	img/comparison.png
	img/hidden_markov.pdf
	img/linest.pdf
	img/linest2.png
	img/normal_cdf.pdf
	img/normal_pdf.pdf
	img/tests.pdf
)

add_latex_document(
	StaSigProc.tex
	FORCE_PDF
  INPUTS ${DRAWINGS}
	IMAGES ${IMAGES}
	DEPENDS writegitid
)
