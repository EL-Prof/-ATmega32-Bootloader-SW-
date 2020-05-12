################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
LSS += \
BLD_SW.lss \

FLASH_IMAGE += \
BLD_SW.hex \

SIZEDUMMY += \
sizedummy \


# All Target
all: BLD_SW.elf secondary-outputs

# Tool invocations
BLD_SW.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,BLD_SW.map -Ttext=0x7000 -mmcu=atmega32 -o "BLD_SW.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

BLD_SW.lss: BLD_SW.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S BLD_SW.elf  >"BLD_SW.lss"
	@echo 'Finished building: $@'
	@echo ' '

BLD_SW.hex: BLD_SW.elf
	@echo 'Create Flash image (ihex format)'
	-avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex BLD_SW.elf  "BLD_SW.hex"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: BLD_SW.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=avr --mcu=atmega32 BLD_SW.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(FLASH_IMAGE)$(ELFS)$(OBJS)$(ASM_DEPS)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) BLD_SW.elf
	-@echo ' '

secondary-outputs: $(LSS) $(FLASH_IMAGE) $(SIZEDUMMY)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
