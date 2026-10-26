# STM32F411 Embedded Systems Fundamentals

Hands-on embedded systems projects developed using the **STM32F411CEU6 Black Pill**, STM32CubeMX, STM32 HAL, Keil MDK, and ST-Link.

This repository documents my step-by-step learning path in STM32 embedded development, from basic GPIO control toward interrupts, timers, communication protocols, ADC, PWM, RTOS, and embedded control applications.

---

## Hardware Platform

| Component | Specification |
|---|---|
| MCU | STM32F411CEU6 |
| Core | ARM Cortex-M4F |
| Board | WeAct STM32F411 Black Pill |
| Debugger | ST-Link V2 |
| Debug Interface | SWD |
| Onboard LED | PC13 |
| External LED | PB0 |
| Push Button | PA0 |

---

## Development Toolchain

- STM32CubeMX
- STM32 HAL
- Keil MDK / µVision
- Arm Compiler 6
- ST-Link V2
- STM32CubeProgrammer
- Git
- GitHub
- PowerShell

---

## Completed Projects

| Project | Topic | Main Peripheral | Status |
|---|---|---|---|
| [01 - GPIO LED Blink](01_gpio_led_blink/) | GPIO Output | PC13 | Completed |
| [02 - GPIO Button Controls LED](02_gpio_button_led/) | GPIO Input / Output | PA0 + PB0 | Completed |

---

## Project 01 - GPIO LED Blink

**Objective:**  
Blink the onboard LED connected to PC13.

### Key Concepts

- GPIO output configuration
- Push-pull output mode
- Active-low LED behavior
- STM32 HAL GPIO API
- Blocking delay using `HAL_Delay()`
- Firmware build and flash workflow

### Main Logic

```c
HAL_GPIO_WritePin(LED_GPIO_Port, LED_Pin, GPIO_PIN_RESET);
HAL_Delay(150);

HAL_GPIO_WritePin(LED_GPIO_Port, LED_Pin, GPIO_PIN_SET);
HAL_Delay(150);
```

Project documentation:

[Open Project 01](01_gpio_led_blink/)

---

## Project 02 - GPIO Button Controls External LED

**Objective:**  
Read a 4-pin tactile push button on PA0 and control an external red LED connected to PB0.

### Key Concepts

- GPIO input configuration
- Internal pull-up resistor
- Active-low button logic
- External LED control
- GPIO input polling
- Pin mapping and hardware wiring
- Conditional control using `if / else`

### Main Logic

```c
if (HAL_GPIO_ReadPin(KEY_GPIO_Port, KEY_Pin) == GPIO_PIN_RESET)
{
    HAL_GPIO_WritePin(RED_LED_GPIO_Port, RED_LED_Pin, GPIO_PIN_SET);
}
else
{
    HAL_GPIO_WritePin(RED_LED_GPIO_Port, RED_LED_Pin, GPIO_PIN_RESET);
}
```

Project documentation:

[Open Project 02](02_gpio_button_led/)

---

## Pin Mapping

| Function | STM32 Pin | Black Pill Label |
|---|---|---|
| Onboard LED | PC13 | C13 |
| Push Button | PA0 | A0 |
| External Red LED | PB0 | B0 |
| SWDIO | PA13 | A13 |
| SWCLK | PA14 | A14 |
| Ground | GND | GND |

---

## Skills Practiced

Through these projects I have practiced:

- STM32 GPIO configuration
- STM32CubeMX project generation
- STM32 HAL programming
- Active-high and active-low digital logic
- Push-button input handling
- LED driving with current-limiting resistor
- SWD debugging
- ST-Link firmware flashing
- Keil MDK project management
- Git version control
- GitHub technical documentation
- Embedded hardware/software integration

---

## Repository Structure

```text
stm32f411-fundamentals/
├── 01_gpio_led_blink/
│   ├── Core/
│   ├── Drivers/
│   ├── MDK-ARM/
│   ├── docs/
│   │   └── images/
│   ├── F411_LED_BLINK.ioc
│   └── README.md
│
├── 02_gpio_button_led/
│   ├── Core/
│   ├── Drivers/
│   ├── MDK-ARM/
│   ├── docs/
│   │   └── images/
│   ├── F411_LED_BLINK.ioc
│   └── README.md
│
├── .gitignore
└── README.md
```

---

## Development Workflow

The general workflow used for each project is:

```text
STM32CubeMX
     ↓
Peripheral Configuration
     ↓
Generate Code
     ↓
Keil MDK
     ↓
Write Application Logic
     ↓
Build
     ↓
ST-Link
     ↓
Flash MCU
     ↓
Hardware Verification
     ↓
Git Commit
     ↓
GitHub Documentation
```

---

## Learning Roadmap

Planned projects:

| Project | Topic | Status |
|---|---|---|
| 01 | GPIO LED Blink | Completed |
| 02 | GPIO Button Input | Completed |
| 03 | GPIO External Interrupt (EXTI) | Planned |
| 04 | UART Communication | Planned |
| 05 | Hardware Timer Interrupt | Planned |
| 06 | PWM Generation | Planned |
| 07 | ADC Analog Acquisition | Planned |
| 08 | I2C Sensor Communication | Planned |
| 09 | SPI Communication | Planned |
| 10 | FreeRTOS Fundamentals | Planned |

---

## Long-Term Direction

The goal of this repository is to build a solid STM32 foundation before moving toward more advanced embedded systems projects involving:

- RC controller firmware
- nRF24L01 wireless communication
- UART / CRSF communication
- PWM servo and ESC control
- Sensors and IMU
- CAN communication
- FreeRTOS
- Embedded control systems
- Autonomous vehicle electronics

---

## Current Status

**Board:** STM32F411CEU6 Black Pill  
**Current level:** GPIO fundamentals  
**Completed projects:** 2  
**Next project:** GPIO External Interrupt (EXTI)