# AgroMonitor-UQ - Prototipo Viable N°1

Sistema de **monitoreo de peso en tiempo real** para una máquina deshidratadora de alimentos.  
El prototipo usa un **ESP32**, un **módulo HX711** y una **celda de carga**, con interfaz web para visualizar y almacenar datos en un archivo CSV.

---

## 🚀 Características principales

- Lectura de peso mediante **HX711 + celda de carga**.  
- Visualización en **interfaz web (ESP32 como servidor WiFi AP)**.  
- Configuración de tiempo de monitoreo y unidad (kg, g, lb).  
- **Exportación de datos** en archivo CSV.  
- **Calibración automática** de la celda desde el **Serial Monitor**.  
- Guardado del factor de calibración en memoria **SPIFFS**.  

---

## 📦 Requisitos de hardware

- ESP32 DevKit (o similar con WiFi).  
- Módulo HX711.  
- Celda de carga (1–5 kg).  
- Pantalla LCD opcional (no requerida en este prototipo).  
- Fuente de 5 V estable.  

---

## 🛠️ Requisitos de software

- [Arduino IDE](https://www.arduino.cc/en/software) versión 1.8.x o 2.x  
- Soporte para **ESP32** en Arduino IDE  
  - En preferencias, añadir URL:  
    ```
    https://dl.espressif.com/dl/package_esp32_index.json
    ```
  - En Gestor de placas: instalar **ESP32 by Espressif Systems**.  
- Librerías necesarias:  
  - **HX711** (Bogdan Necula o similar).  
  - Incluidas en Arduino IDE: `WiFi.h`, `WebServer.h`, `SPIFFS.h`.  

---

## ⚙️ Compilación y carga

1. Clonar este repositorio o descargarlo en tu PC:  
   ```bash
   git clone https://github.com/juandtobarg-create/AgroMonitor-UQ.git
2. Abrir Arduino IDE.
3. Seleccionar la placa:
   Herramientas → Placa → ESP32 Arduino → ESP32 Dev Module.
4. Abrir el archivo:
   src/CDIO-3-WIFI.ino
5. Conectar la ESP32 por USB.
6. Compilar y cargar con → Upload.

## ▶️ Ejecución

1. Al encender, la ESP32 crea una red WiFi:
  -SSID: AgroMonitor-UQ
  -Contraseña: 12345678

2. Conectarse a esa red desde un PC o celular.
3. Abrir en el navegador:
    http://192.168.4.1

4. En la interfaz web se puede:
   -Definir tiempo de monitoreo.
   -Escoger la unidad (kg, g, lb).
   -Iniciar/Detener monitoreo.
   -Descargar el archivo CSV.
