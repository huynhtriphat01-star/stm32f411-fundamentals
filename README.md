# STM32F411 Embedded Systems Fundamentals

Hands-on embedded systems projects developed on STM32F411CEU6 Black Pill using STM32CubeMX, STM32 HAL, Keil MDK and ST-Link/SWD.

## Hardware

- MCU: STM32F411CEU6
- Board: STM32F411 Black Pill
- Debugger: ST-Link V2
- Programming Interface: SWD

## Development Environment

- STM32CubeMX
- STM32 HAL
- Keil MDK
- Arm Compiler 6
- ST-Link / SWD

## Projects

| # | Project | Concepts | Status |
|---|---|---|---|
| 01 | GPIO LED Blink | GPIO Output, HAL, Timing | Completed |
| 02 | Button Controls External LED | GPIO Input, Pull-up, GPIO Output | Completed |
| 03 | EXTI Button Interrupt | Interrupt, NVIC, Debounce | Planned |
| 04 | UART Communication | UART TX/RX | Planned |
| 05 | Hardware Timer | Timer Interrupt | Planned |
| 06 | PWM | PWM Generation | Planned |
| 07 | ADC | Analog Acquisition | Planned |
| 08 | I2C | Sensor Communication | Planned |

## Pin Mapping

| Function | STM32 Pin | Black Pill Label |
|---|---|---|
| Onboard LED | PC13 | C13 |
| Push Button | PA0 | A0 |
| External Red LED | PB0 | B0 |
| SWDIO | PA13 | A13 |
| SWCLK | PA14 | A14 |

## Repository Structure

```text
stm32f411-fundamentals/
├── 01_gpio_led_blink/
├── 02_gpio_button_led/
├── docs/
│   └── images/
├── .gitignore
└── README.md