# 项目名称，编译生成的 hex和bin名称
TARGET = Demo

# 是否会进行调试
DEBUG = 1

# optimization    ## 选择优化等级，优化等级低->高，可参考Keil的设置，如果程序运行不理想，优化程序或降低优化等级
#OPT = -O0        ## 没有优化。
#OPT = -O1        ## 编译器试图减少代码大小和执行时间，而不执行任何花费大量编译时间的优化。
OPT = -Og         ## 参数 -Og 是在 -O1 的基础上，去掉了那些影响调试的优化告诉编译器，编译后的代码不要影响调试，但调试信息的生成还是靠 -g 参数的。
#OPT = -O2        ## 更加优化。GCC执行几乎所有支持的优化，不涉及空间速度权衡。此选项既增加编译时间，提高了生成代码的性能。
#OPT = -O3        ## 优化更多。
#OPT = -Os        ## 优化大小。启用所有优化，除了那些经常增加代码大小
#OPT = -Ofast     ## 不遵守严格的标准。使所有优化。它还支持并非对所有符合标准的程序都有效的优化。

# Build path      ## Build编译产生的文件存放目录 , Output生成hex与bin的存放位置
BUILD_DIR = Build
OUT_DIR = Output

# source                           ## 检索项目目录下的c文件的，注意C大小写
C_SOURCES := $(wildcard */*/*/*/*/*/*/*.c) \
	$(wildcard */*/*/*/*/*/*.c) \
	$(wildcard */*/*/*/*/*.c) \
	$(wildcard */*/*/*/*.c) \
	$(wildcard */*/*/*.c) \
	$(wildcard */*/*.c) \
	$(wildcard */*.c)
# C_SOURCES =  \
# User/main.c\
# User/stm32f10x_it.c \
# User/system_stm32f10x.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/misc.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_adc.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_bkp.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_can.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_cec.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_crc.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_dac.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_dbgmcu.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_dma.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_exti.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_flash.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_fsmc.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_gpio.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_i2c.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_iwdg.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_pwr.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_rcc.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_rtc.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_sdio.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_spi.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_tim.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_usart.c \
# src/Libraries/STM32F10x_StdPeriph_Driver/src/stm32f10x_wwdg.c \
# src/Libraries/CMSIS/CoreSupport/core_cm3.c \


# ASM sources                      ## 检索项目目录下的s汇编文件的，注意s是小写
ASM_SOURCES  := $(wildcard */*/*/*/*/*/*/*.s) \
	$(wildcard */*/*/*/*/*/*.s) \
	$(wildcard */*/*/*/*/*.s) \
	$(wildcard */*/*/*/*.s) \
	$(wildcard */*/*/*.s) \
	$(wildcard */*/*.s) \
	$(wildcard */*.s)
# ASM_SOURCES =  \
# src/Libraries/CMSIS/DeviceSupport/startup_stm32f10x_hd.s

# C includes                       ## 添加 h头文件的 Include路径，格式 -I + 路径，添加文件夹注意在此添加include
C_INCLUDES =  \
-IUser \
-Isrc/Libraries/CMSIS/CoreSupport \
-Isrc/Libraries/CMSIS/DeviceSupport \
-Isrc/Libraries/STM32F10x_StdPeriph_Driver/inc \

# AS includes                     ## 添加 汇编的 Include路径，格式 -I + 路径，添加文件夹注意在此添加include
AS_INCLUDES =

# C defines                       ## 添加全局 Define ，std库参照stm32f10x.h，换芯片需更换 宏定义，格式 -D + dd
C_DEFS =  \
-DSTM32F10X_HD \
-DUSE_STDPERIPH_DRIVER \

# link script                    ## 添加 ld链接 文件，注意路径
LDSCRIPT = STM32F103ZETx_FLASH.ld

# cpu                             ## 参照 stm32cube
CPU = -mcpu=cortex-m3

# fpu
# NONE for Cortex-M0/M0+/M3

# float-abi

# mcu
MCU = $(CPU) -mthumb $(FPU) $(FLOAT-ABI)

# macros for gcc
# AS defines
AS_DEFS =

GCC_PATH = "C:\\ST\\STM32CubeIDE_1.6.0\\STM32CubeIDE\\plugins\\com.st.stm32cube.ide.mcu.externaltools.gnu-tools-for-stm32.9-2020-q2-update.win32_1.5.0.202011040924\\tools\\bin"
#######################################

#######################################
# binaries
#######################################
PREFIX = arm-none-eabi-
# The gcc compiler bin path can be either defined in make command via GCC_PATH variable (> make GCC_PATH=xxx)
# either it can be added to the PATH environment variable.
ifdef GCC_PATH
CC = $(GCC_PATH)/$(PREFIX)gcc
AS = $(GCC_PATH)/$(PREFIX)gcc -x assembler-with-cpp
CP = $(GCC_PATH)/$(PREFIX)objcopy
SZ = $(GCC_PATH)/$(PREFIX)size
else
CC = $(PREFIX)gcc
AS = $(PREFIX)gcc -x assembler-with-cpp
CP = $(PREFIX)objcopy
SZ = $(PREFIX)size
endif
HEX = $(CP) -O ihex
BIN = $(CP) -O binary -S


# compile gcc flags
ASFLAGS = $(MCU) $(AS_DEFS) $(AS_INCLUDES) $(OPT) -Wall -fdata-sections -ffunction-sections

CFLAGS = $(MCU) $(C_DEFS) $(C_INCLUDES) $(OPT) -Wall -fdata-sections -ffunction-sections

ifeq ($(DEBUG), 1)
CFLAGS += -g -gdwarf-2
endif


# Generate dependency information
CFLAGS += -MMD -MP -MF"$(@:%.o=%.d)"

# libraries
LIBS = -lc -lm -lnosys
LIBDIR =
LDFLAGS = $(MCU) -specs=nano.specs -T$(LDSCRIPT) $(LIBDIR) $(LIBS) -Wl,-Map=$(BUILD_DIR)/$(TARGET).map,--cref -Wl,--gc-sections

# default action: build all
all: $(BUILD_DIR)/$(TARGET).elf $(OUT_DIR)/$(TARGET).hex $(OUT_DIR)/$(TARGET).bin


#######################################
# build the application
#######################################
# list of objects
OBJECTS = $(addprefix $(BUILD_DIR)/,$(notdir $(C_SOURCES:.c=.o)))
vpath %.c $(sort $(dir $(C_SOURCES)))
# list of ASM program objects
OBJECTS += $(addprefix $(BUILD_DIR)/,$(notdir $(ASM_SOURCES:.s=.o)))
vpath %.s $(sort $(dir $(ASM_SOURCES)))

$(BUILD_DIR)/%.o: %.c Makefile | $(BUILD_DIR)
	$(CC) -c $(CFLAGS) -Wa,-a,-ad,-alms=$(BUILD_DIR)/$(notdir $(<:.c=.lst)) $< -o $@

$(BUILD_DIR)/%.o: %.s Makefile | $(BUILD_DIR)
	$(AS) -c $(CFLAGS) $< -o $@

$(BUILD_DIR)/$(TARGET).elf: $(OBJECTS) Makefile
	$(CC) $(OBJECTS) $(LDFLAGS) -o $@
	$(SZ) $@

$(OUT_DIR)/%.hex: $(BUILD_DIR)/%.elf | $(OUT_DIR)
	$(HEX) $< $@

$(OUT_DIR)/%.bin: $(BUILD_DIR)/%.elf | $(OUT_DIR)
	$(BIN) $< $@

$(BUILD_DIR):
	mkdir $@

$(OUT_DIR):
	mkdir $@

#######################################
# clean up
#######################################
clean:
	-rm -fR $(BUILD_DIR)

#######################################
# dependencies
#######################################
-include $(wildcard $(BUILD_DIR)/*.d)

# *** EOF ***
