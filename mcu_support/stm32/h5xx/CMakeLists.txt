add_library(st_h5_support STATIC
    system_stm32h5xx.c
)

target_include_directories(st_h5_support PUBLIC .)
target_link_libraries(st_h5_support PUBLIC
    cmsis
    st_h5_hal
)

add_subdirectory(HAL)