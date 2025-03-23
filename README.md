# STM32 DHT11 HAL Library
Library for reading data from DHT11 humidity and temperature sensor.\
Tested on Nucleo-F767ZI

## Requirements
- HAL
- Set timer that you want to use to 1us
- Configure data pin to usart in Single Wire (Half-Duplex) mode

## Usage
First create 2 uint16 variables for temperature and humidity, then create a DHT11 structure and provide it with appropriate arguments:

```
uint16_t temperature, humidity;
struct DHT11 dht = {
  GPIOA,
  GPIO_PIN_0,
  &temperature,
  &humidity,
  &htim4
};
```
After that you can read data from the sensor with:
```
DHT11_ReadData(&dht);
```
