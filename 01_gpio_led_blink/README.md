# Project 01 - GPIO LED Blink

## Objective

Blink the onboard LED of the STM32F411CEU6 Black Pill using GPIO output and STM32 HAL.

## Hardware

- STM32F411CEU6 Black Pill
- ST-Link V2
- SWD interface
- Onboard LED connected to PC13

## Pin Mapping

| Function | STM32 Pin | Board Label |
|---|---|---|
| Onboard LED | PC13 | C13 |
| SWDIO | PA13 | A13 |
| SWCLK | PA14 | A14 |

## GPIO Configuration

PC13:

- GPIO Output
- Push-Pull
- No pull-up / pull-down
- Low speed
- User Label: `LED`

The onboard LED is active-low:

- GPIO LOW -> LED ON
- GPIO HIGH -> LED OFF

## Main Logic

```c
HAL_GPIO_WritePin(LED_GPIO_Port, LED_Pin, GPIO_PIN_RESET);
HAL_Delay(150);

HAL_GPIO_WritePin(LED_GPIO_Port, LED_Pin, GPIO_PIN_SET);
HAL_Delay(150);
```

## Step-by-Step Visual Guide

![STM32F411 LED blink guide](docs/images/project01_led_blink_guide.png)

![STM32CubeMX GPIO configuration](docs/images/project01_cubemx_gpio_config.png)

![Keil main code](docs/images/project01_keil_main_code.png)

![Build and flash result](docs/images/project01_build_flash_result.png)
