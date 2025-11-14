# Desarollo en Zephyr para ESP32-S3
Configuración de Zephyr RTOS mínimo para Espressif ESP32-S3, sin sobrecarga y rápido.

El objetivo es tener un Workspace de Zephyr para desarrollo con el SoC de Espressif ESP32-S3, que ocupe lo mínimo y que sea rápido de montar.
Para desarrollo en _Windows 11_ (sin usar WSL), y con el IDE VSCode, y el plugin _Zephyr IDE_. 

Requerimientos:
- [Zephyr RTOS v4.3.0](https://github.com/zephyrproject-rtos/zephyr.git "Zephyr RTOS v4.3.0").
- [Zephyer SDK v0.17.4](https://github.com/zephyrproject-rtos/sdk-ng/tree/v0.17.4 "Zephyr SDK v0.17.4") (1.0.0 cuando salga de la Beta)
  con solo el Toolchain de Espressif.
- [Hal de Espressif](https://github.com/zephyrproject-rtos/hal_espressif) solo para ESP32-S3.

  
