#add_subdirectory(periph) folders
#add_subdirectory(utils) folders

# Make core consumers also get utils and chip_select by adding them to the INTERFACE core target
# `core` is defined in the parent `common/CMakeLists.txt` as an INTERFACE target.
if (TARGET core)
	target_link_libraries(core INTERFACE #folder targets
		utils
		periph
	)
endif()
