include(ExportDirectory)
set(SOURCE_FILES
	circle-buffer.c
	configuration.c
	convolve.c
	crc32.c
	elf-read.c
	export.c
	formatting.c
	gbk-table.c
	hash.c
	patch.c
	patch-fast.c
	patch-ips.c
	patch-ups.c
	png-io.c
	ring-fifo.c
	string.c
	table.c
	text-codec.c
	vfs.c)

set(GUI_FILES
	gui.c
	gui/file-select.c
	gui/font.c
	gui/font-metrics.c
	gui/menu.c)

set(TEST_FILES
	test/string-parser.c
	test/string-utf8.c
	test/text-codec.c
	test/vfs.c)

if(NOT DEFINED OS_SRC)
	set(OS_FILES memory.c)
	export_directory(OS OS_FILES)
endif()

source_group("Utilities" FILES ${SOURCE_FILES})
source_group("GUI source" FILES ${GUI_FILES})
source_group("Utilities tests" FILES ${TEST_FILES})

export_directory(UTIL SOURCE_FILES)
export_directory(GUI GUI_FILES)
export_directory(UTIL_TEST TEST_FILES)
