# 🛡️ Sistema Abierto de Contención Volumétrica 3D y Bienestar Animal
### *Arquitectura "Canasta Básica Tecnológica" — Hardware y Software Libre para la Protección Ética de Fauna*

[![License: CERN-OHL-S v2](https://img.shields.io/badge/Hardware-CERN--OHL--S%20v2-00599C?style=flat-square)](https://ohwr.org/cernohl)
[![License: GPL v3](https://img.shields.io/badge/Software-GPLv3-blue?style=flat-square)](https://www.gnu.org/licenses/gpl-3.0)
[![Platform](https://img.shields.io/badge/MCU-ESP32--S3%20%7C%20nRF52840-red?style=flat-square)]()
[![RF Tech](https://img.shields.io/badge/Tracking-UWB%20%2B%20mmWave%2060GHz-green?style=flat-square)]()
[![Status](https://img.shields.io/badge/Estado-Prototipo%20Funcional-orange?style=flat-square)]()

> **Cero choques eléctricos. Cero suscripciones. Cero lucro.**  
> Una cerca virtual tridimensional de precisión sub-métrica que sustituye el castigo físico por **condicionamiento operante bioacústico y olfativo**, diseñada bajo un esquema de **Fondo Social Cero Ganancia** donde el 100% de los remanentes netos se destinan a refugios y campañas de esterilización animal.

---

## 🎯 ¿Por qué este proyecto?

Los sistemas comerciales de contención animal presentan tres fallas críticas: **son costosos y cerrados**, operan solo en 2D (ignoran bardas, balcones y tejados) y **recurren a descargas eléctricas** que generan estrés crónico y agresividad.

Este proyecto democratiza el sensado espacial de grado industrial para crear una **malla volumétrica 3D invisible** capaz de anticipar la trayectoria de salto de una mascota en menos de **50 ms** y guiarla de vuelta a una zona segura sin violencia.

---

## 🏗️ Arquitectura del Sistema

El flujo operativo de hardware y software se interconecta en cuatro etapas secuenciales de baja latencia (< 50 ms):

* **1. Captación Perimetral y Telemetría (Anclas Solares ↔ Nodo Móvil):**
  * **4x Anclas Perimetrales Solares (UWB + Radar mmWave 60 GHz)** intercambian paquetes de Tiempo de Vuelo (*ToF*) con el **Nodo Móvil: Collar IP67 (ESP32-S3 / nRF52840)**.
* **2. Fusión Sensorial y Digitalización 3D:**
  * Las anclas alimentan al **Módem Catastral (SLAM)** para digitalizar el perímetro en coordenadas $(X, Y, Z)$, mientras el collar procesa su **IMU de 6 ejes + Edge AI** mediante un **Filtro Kalman (< 50 ms)** para calcular trayectoria y aceleración vertical.
* **3. Evaluación Lógica (Núcleo de Decisión):**
  * Ambos flujos convergen en la **Máquina de Estados Finitos (Gradiente No Violento)**, que determina la posición exacta del animal respecto a las fronteras tridimensionales.
* **4. Ejecución de Estímulos Bioacústicos y Olfativos:**
  * **Nivel 1-2 (Pre-alerta / Disuasión):** Activación de vibración háptica + pulso ultrasónico direccional.
  * **Nivel 3 (Bloqueo):** Emisión de eco acústico disuasivo continuo.
  * **Zona 0 (Faro Biológico):** Corte de disuasión y liberación de micro-frecuencia armónica + aroma calmante.

---

## ⚙️ Módulos Principales

### 1. Módem Catastral y Geometría Volumétrica 3D (SLAM)
* Combina transceptores **UWB** (Qorvo/Decawave) y micro-radares **mmWave (24/60 GHz)** mediante barridos de Tiempo de Vuelo (*Time of Flight*).
* Autocalibra las anclas perimetrales y digitaliza el espacio en coordenadas $(X, Y, Z)$ sin mediciones manuales.
* **Predicción Vectorial de Salto:** Evalúa velocidad y aceleración vertical; si el animal perfila un salto hacia una barda o techo, activa la disuasión antes del despegue.

### 2. Matriz de Energía e Infraestructura Física
* **Anclas Fijas:** Paneles solares monocristalinos + baterías $\text{LiFePO}_4$ de ciclo profundo para autonomía continua a la intemperie.
* **Collar Móvil:** SoC ESP32-S3 / nRF52840 en *Deep Sleep* con despertar por pings ultrasónicos e IMU. Carga inductiva o cinética.
* **Blindaje IP67:** Carcasa impresa en 3D en **TPU Shore 95A** con empaque de silicona y encapsulado epóxico.

### 3. Gradiente Conductual (Máquina de Estados Finitos)

| Estado / Zona | Criterio Espacial | Estímulo Activo | Objetivo Conductual |
| :--- | :--- | :--- | :--- |
| **Nivel 1: Pre-alerta** | A 50 cm del límite 3D | Vibración háptica suave + tono de 15 kHz | Advertencia temprana de frontera |
| **Nivel 2: Disuasión** | Contacto con límite 3D | Pulso ultrasónico direccional (22–30 kHz) | Fricción acústica incómoda (sin dolor) |
| **Nivel 3: Bloqueo** | Exteriorización (+10 cm) | Eco sonoro continuo de frecuencia disuasiva | Delimitación firme de zona no confortable |
| **Vector de Retorno** | Giro hacia el interior | Corte inmediato de todo estímulo disuasivo | **Refuerzo negativo:** alivio instantáneo |
| **Zona 0: Faro Biológico** | Retorno al centro seguro | Micro-frecuencia armónica + **Actuador Térmico de Aroma** (esencia de atún / *catnip*) | **Refuerzo positivo:** asociación de calma |

### 4. Edge AI de Voz y Privacidad por Diseño
* Reconocimiento local (*TinyML / Wake-Word*) de la firma vocal del tutor para abrir pasillos temporales de paseo o emitir llamados de emergencia.
* **Cero nube:** El búfer de audio en RAM se sobrescribe cada 500 ms. Ninguna grabación sale del dispositivo.

### 5. Protocolo de Emergencia Escalonado (*Fail-Safe*)
* **Filtro Kalman:** Elimina falsos positivos por rebotes de señal.
* **Sismo o Incendio:** Detección telúrica (> 0.3g) o térmica crítica desactiva automáticamente la cerca para permitir la libre evacuación.
* **Dead-Man's Switch:** Ante fallo crítico o caída de voltaje, el hardware se desenergiza por completo convirtiendo el collar en una correa textil inerte.

---

## 💰 Viabilidad Económica y BOM (Prototipo)

Al utilizar módulos comerciales estándar (*Off-The-Shelf*) y vincular el desarrollo de firmware con residencias profesionales universitarias, la barrera de entrada se reduce en un **90%** frente a la industria tradicional.

### Lista de Materiales (1 Nodo Maestro + 4 Anclas Solares + 1 Collar)

| Componente | Especificación | Costo Est. (USD) |
| :--- | :--- | :---: |
| **6x Módulos RF** | UWB DWM1000 / Radar mmWave 24–60 GHz | $45.00 |
| **6x Microcontroladores** | ESP32-S3 / Nordic nRF52840 | $24.00 |
| **4x Sistema Solar** | Celdas 5V 100mA + Cargador + Baterías $\text{LiFePO}_4$ | $16.00 |
| **1x Audio Edge AI** | Micrófono MEMS I2S omnidireccional | $3.50 |
| **1x Faro Olfativo** | Actuador térmico miniatura + cámara sellada | $4.50 |
| **Carcasas IP67** | Filamento TPU + resina epóxica + empaques | $12.00 |
| **Varios** | Transductor piezo, PCB prototipo, correa y tornillería | $10.00 |
| **TOTAL SISTEMA COMPLETO** | *Costo por collar adicional: ~$25.00 USD* | **$115.00 USD** |

* **Inversión Fase Prototipo Funcional (3 meses):** $2,300.00 USD (incluye becas para 2 residentes de ingeniería, 3 lotes de PCBs, banco de pruebas y registros abiertos).

---

## 🗺️ Hoja de Ruta (Roadmap)

* [x] **Fase 1 (Mes 1):** Selección de componentes, arquitectura de firmware UWB/ESP32 y pruebas de *Wake-Word* local en laboratorio.
* [ ] **Fase 2 (Mes 2):** Calibración del *Módem Catastral* (SLAM 3D), manufactura de carcasas TPU IP67 e integración del actuador térmico olfativo.
* [ ] **Fase 3 (Mes 3):** Validación etológica en campo, pruebas de desactivación sísmica (*Dead-Man's Switch*) y liberación total de esquemáticos (KiCad), STLs y código.

---

## 🤝 Modelo Social y Licenciamiento

* **Hardware:** Liberado bajo licencia **CERN-OHL-S v2** (puedes fabricarlo, modificarlo y distribuirlo manteniendo las fuentes abiertas).
* **Software / Firmware:** Liberado bajo **GNU GPLv3**.
* **Fondo Social Cero Ganancia:** Cualquier taller o cooperativa que comercialice kits ensamblados bajo este sello se compromete a operar al costo de manufactura y destinar el **100% de los remanentes netos** a organizaciones registradas de rescate y esterilización animal.[cite: 1]
