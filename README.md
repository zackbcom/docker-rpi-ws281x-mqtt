# Control WS281x from Docker

For supported GPIOs please see [rpi-ws281x-python](https://github.com/rpi-ws281x/rpi-ws281x-python/blob/master/library/README.rst)

## Environmental variables
- `LED_GPIO` *(required)*
- `LED_COUNT` *(required)*
- `LED_CHANNEL` *(optional; default=0)*
- `LED_FREQ_HZ` *(optional; default=800000; 400000 or 800000)*
- `LED_DMA_NUM` *(optional; default=10; range=0-14)*
- `LED_BRIGHTNESS` *(optional; default=255; range=1-255)*
- `LED_INVERT` *(optional; default=0; 1 or 0)*


`docker-compose.yml`
```yaml
version: "3.6"
services:  
  rpi_ws281x:
    container_name: rpi_ws281x
    restart: always
    build: ./docker-homeassistant-ws281x
    privileged: true
    environment:
      - LED_GPIO=12
      - LED_COUNT=10
```