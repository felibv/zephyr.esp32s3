# Desarollo en Zephyr para ESP32-S3
Configuración de Zephyr RTOS mínimo para Espressif ESP32-S3, sin sobrecarga y rápido.

El objetivo es tener un Workspace de Zephyr para desarrollo con el SoC de Espressif ESP32-S3, que ocupe lo mínimo y que sea rápido de montar.
Para desarrollo en _Windows 11_ (sin usar el Windows Subsystem for Linux _WSL_), y con el IDE VSCode, y el plugin _Zephyr IDE_. 

Requerimientos:
- [Zephyr RTOS v4.3.0](https://docs.zephyrproject.org/4.3.0/releases/release-notes-4.3.html "Zephyr RTOS release v4.3.0").
- [Zephyer SDK](https://docs.zephyrproject.org/4.3.0/develop/toolchains/zephyr_sdk.html "Zephyr SDK Toolchains") v0.17.4 (1.0.0 cuando salga de la Beta)
  con únicamente el Toolchain de Espressif.
- [Hal de Espressif](https://github.com/zephyrproject-rtos/hal_espressif) solo para ESP32-S3 (MCU Xtensa)

  
Partimos de la documentación oficial [Getting Started Guide](https://docs.zephyrproject.org/4.3.0/develop/getting_started/index.html)

1. Instalar dependencias usando [winget](https://learn.microsoft.com/en-us/windows/package-manager/ "Instalar el gestor de paquetes winget").
```
    winget install Kitware.CMake Ninja-build.Ninja oss-winget.gperf Python.Python.3.12 Git.Git oss-winget.dtc wget 7zip.7zip
```
  (el directorio a 7z.exe lo has de añadir manualmente a tu PATH)
  
2. Montar el entorno virtual de Phyton y descargar _west_
    1. Abre un PowerShell, y ponte en tu _Home directory_ o en tu carpeta de desarrollo (para el Workspace de west usaremos el directorio con nombre _zephyr.esp32s3_)
    ```
     cd $Env:HOMEPATH
     python -m venv zephyr.esp32s3\.venv
    ```
    2. Tenemos que permitir la ejecución de scripts en la sesión de Powershell
    ```
     Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
    ```
    3. Activamos el entorno virtual de Python
    ```
     zephyr.esp32s3\.venv\Scripts\Activate.ps1
    ```
    4. Insalamos _West_
    ```
     pip install west
    ```
  
Ahora es cuando empezamos con la magia.

3. Baja el fichero manifest_min_esp32s3.yml de este repositorio y ponlo en el directorio zephyr.esp32s3
4. Ejecuta en el directorio zephyr.esp32s3\ el comando para inicializar el workspace de west
```
   cd ~/zephur.esp32s3
   west init -l . --manifest-file=manifest_min_esp32s3.yml
```
5. 
