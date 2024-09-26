# STM32H7-Ethernet-issue-solved
A solution to ethernet not working on STM32H7 MCUs (Tested on H753ZI Nucleo-board)

the ethernet drivers in the (stm32h7xx_HAL_Drivers) has an issue working in some MCUs in my case (H753ZI nucleo board) 
In order to solve such issues, you must change the ethernet drivers of your project with the working old ones, You can replace the files or change the content of the drivers directly from STMcubeIDE, in your project tree find the (STM32H7xx_HAL_Driver) and in (Inc) folder change the content of the (stm32h7xx_hal_eth.h) and the (stm32h7xx_hal_eth_ex.h) in your project tree with the content of the included (.h) files, after that open the (Src) folder and change the content of the (stm32h7xx_hal_eth.c) and the (stm32h7xx_hal_eth_ex.c) files to the ones included, and then do the same for the files (ethernetif.c) and (ethernetif.h) in (LWIP, Target) folder and you should be ok after that.

These changes should be enough to get you running but if the project didn't work after doing the changes ubove you can change more files in according to the project I uploaded such as the files in the (LWIP) folder, After that no more changes is needed.

(Notice that the project is using an OS (freeRTOS). The project is working perfeclty you can use it in order to find the right ram addresses, MPU config., ETH, and LWIP settings)

