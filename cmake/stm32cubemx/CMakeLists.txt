cmake_minimum_required(VERSION 3.22)

project(stm32cubemx)
add_library(stm32cubemx INTERFACE)

# Enable CMake support for ASM and C languages
enable_language(C ASM)

target_compile_definitions(stm32cubemx INTERFACE 
	USE_HAL_DRIVER 
	STM32F031x6
    $<$<CONFIG:Debug>:DEBUG>
)

target_include_directories(stm32cubemx INTERFACE
    ../../Core/Inc
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Inc
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Inc/Legacy
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/CMSIS/Device/ST/STM32F0xx/Include
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/CMSIS/Include
)

target_sources(stm32cubemx INTERFACE
    ../../Core/Src/main.c
    ../../Core/Src/stm32f0xx_it.c
    ../../Core/Src/stm32f0xx_hal_msp.c
    ../../Core/Src/stm32f0xx_hal_timebase_tim.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_i2c.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_i2c_ex.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_rcc.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_rcc_ex.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_gpio.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_dma.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_cortex.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_pwr.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_pwr_ex.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_flash.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_flash_ex.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_exti.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_spi.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_spi_ex.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_tim.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_tim_ex.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_uart.c
    /Users/sohal/STM32Cube/Repository/STM32Cube_FW_F0_V1.11.5/Drivers/STM32F0xx_HAL_Driver/Src/stm32f0xx_hal_uart_ex.c
    ../../Core/Src/system_stm32f0xx.c
    ../../Core/Src/sysmem.c
    ../../Core/Src/syscalls.c
    ../../startup_stm32f031x6.s
)

target_link_directories(stm32cubemx INTERFACE
)

target_link_libraries(stm32cubemx INTERFACE
)

# Validate that STM32CubeMX code is compatible with C standard
if(CMAKE_C_STANDARD LESS 11)
    message(ERROR "Generated code requires C11 or higher")
endif()


