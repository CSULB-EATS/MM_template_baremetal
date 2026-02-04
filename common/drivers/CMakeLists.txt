# add_subdirectory(platform/stm32f4) # Directory does not exist yet. Uncomment when ready.

add_library(driver INTERFACE)

target_include_directories(driver INTERFACE
    bus
    io 
)

target_link_libraries(driver INTERFACE
    hal
    
)