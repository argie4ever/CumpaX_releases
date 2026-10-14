<p align="center">
  <img width="240" height="240" alt="CumpaX_logo" src="https://github.com/user-attachments/assets/6c88ae87-6aca-4bf4-8b60-abb7ddd62d08" />
</p>


# Cumpa X (v1.0.0)

[![Release](https://img.shields.io/badge/Release-v1.0.0-blue?style=for-the-badge)](https://github.com/arielledesmabecerra/Cumpa_X_Releases/releases/latest)
[![Platform](https://img.shields.io/badge/Platform-macOS%2014.0%2B-000000?style=for-the-badge&logo=apple)](https://github.com/arielledesmabecerra/Cumpa_X_Releases/releases/latest)
[![Apple Silicon & Intel](https://img.shields.io/badge/Architecture-Universal%20Binary-gray?style=for-the-badge&logo=apple)](https://github.com/arielledesmabecerra/Cumpa_X_Releases/releases/latest)
[![Cafecito](https://img.shields.io/badge/Cafecito-Argentina-blue?style=for-the-badge&logo=coffee)](https://cafecito.app/arielledesmabecerra)
[![Ko-fi](https://img.shields.io/badge/Ko--fi-Donar_USD-ff5e5b?style=for-the-badge&logo=ko-fi)](https://ko-fi.com/arielledesmabecerra)

---

### ☕ Apoya el proyecto / Support Independent Development

Cumpa X es una herramienta de código abierto y distribución gratuita para editores, documentalistas y asistentes de montaje. Si optimiza tu tiempo o el flujo de trabajo de tu productora, puedes colaborar para sostener su desarrollo continuo:

* 🇦🇷 **Argentina (Transferencia bancaria / Mercado Pago en ARS):**  
  👉 [**Invitar un Cafecito**](https://cafecito.app/arielledesmabecerra)

* 🌎 **Internacional (Tarjeta de crédito / Débito / PayPal en USD):**  
  👉 [**Support on Ko-fi**](https://ko-fi.com/arielledesmabecerra)

---

## 🇪🇸 Descripción General

**Cumpa X** es una herramienta de automatización para **Apple Final Cut Pro (FCPX)** diseñada para eliminar las tareas más lentas, repetitivas y propensas a errores en el montaje profesional, documental y televisivo.

### Funcionalidades Principales

* **Minutados y Transcripciones Inteligentes:**
  * Convierte archivos de texto plano o Markdown (`.txt`, `.md`) en colecciones de **Palabras Clave (Keywords)** por rango dentro del navegador de FCPX.
  * Ensambla automáticamente secuencias de **Primer Corte (Rough Cuts)** en el timeline con marcadores descriptivos y títulos de bloque.
  * Detección matemática automática de la base de tiempo (framerate) del proyecto base (`.fcpxml` / `.fcpxmld`) para evitar desfasajes.

* **Aplanado Multicámara (*Flatten Multicam*):**
  * Transforma contenedores multicámara (`<mc-clip>`) en clips individuales directos en la línea de tiempo principal, listos para exportar a **DaVinci Resolve** (color) o **Pro Tools / Fairlight** (sonido).
  * Genera una **Pista de Referencia A/B** en el carril superior para verificar la sincronía cuadro por cuadro activando/desactivando con la tecla `V`.
  * **Consolidación de audio continuo:** Elimina micro-cortes innecesarios en tomas continuas de micrófonos lavalier o boom.
  * Preserva reencuadres (Scale/Position), transformaciones espaciales y correcciones de color aplicadas al corte.

* **Conversor Premiere XML a FCPXML:**
  * Migra secuencias de Adobe Premiere Pro (`.xml` XMEML) a proyectos nativos de Final Cut Pro (`.fcpxml` 1.10).
  * Estrategia de Storyline **Universal Gap** para garantizar sincronía total sin colisiones de pistas.

### Requisitos del Sistema
* **Sistema Operativo:** macOS 14.0 (Sonoma) o superior.
* **Apple Final Cut Pro:** Versión 10.6 o superior.
* **Arquitectura:** Binario universal nativo para **Apple Silicon (M1/M2/M3/M4)** y procesadores **Intel**.

### Instalación
1. Descarga el instalador `Cumpa-X-1.0.0-macOS.dmg` desde los enlaces inferiores o la sección de [Releases](https://github.com/arielledesmabecerra/Cumpa_X_Releases/releases/latest).
2. Arrastra `Cumpa X.app` a tu carpeta de **Aplicaciones**.
3. **Primera ejecución:** Haz clic derecho (o `Control + Clic`) sobre la aplicación y selecciona **Abrir** para confirmar la excepción de seguridad de macOS.

---

## 🇺🇸 Overview

**Cumpa X** is a dedicated automation workflow assistant for **Apple Final Cut Pro (FCPX)**, engineered to remove repetitive, high-friction, and error-prone tasks in documentary, multi-camera, and narrative post-production.

### Key Features

* **Smart Transcripts & Timecode Ingestion:**
  * Parses plain text and Markdown timecoded scripts (`.txt`, `.md`) into range-based **Keywords** directly in the FCPX Event Browser.
  * Auto-assembles **Rough Cut Timelines** with labeled markers and thematic clip sections in seconds.
  * Automatic project framerate detection (`.fcpxml` / `.fcpxmld`) ensuring sub-frame sync precision.

* **Multicam Flattening (*Flatten Multicam*):**
  * Solves FCPX's native export bottleneck by flattening multicam containers (`<mc-clip>`) into discrete, individual timeline clips ready for **DaVinci Resolve** color grading or **Pro Tools / Fairlight** sound post.
  * Injects a continuous **A/B Reference Track** in Lane 1 (toggle with key `V` to visually audit every cut).
  * **Continuous audio consolidation:** Eradicates micro-edits across continuous lav/boom microphones.
  * Inherits scale, position transforms, and shot-level color adjustments.

* **Premiere XML to FCPXML Translation:**
  * Cleanly migrates Adobe Premiere Pro sequences (`.xml` XMEML) into native Final Cut Pro projects (`.fcpxml` 1.10).
  * **Universal Gap** storyline mapping to guarantee rock-solid timing and stem integrity.

### System Requirements
* **Operating System:** macOS 14.0 (Sonoma) or higher.
* **Apple Final Cut Pro:** Version 10.6 or higher.
* **Architecture:** Universal binary (Native Apple Silicon M1/M2/M3/M4 & Intel 64-bit).

---

## 📦 Descargas / Direct Downloads

| Plataforma | Archivo | Arquitectura |
| :--- | :--- | :--- |
| **macOS** | [**`Cumpa-X-1.0.0-macOS.dmg`**](https://github.com/arielledesmabecerra/Cumpa_X_Releases/releases/latest/download/Cumpa-X-1.0.0-macOS.dmg) | Apple Silicon & Intel (Universal) |

---

## 📖 Documentación / Documentation

Consulta la guía operativa completa paso a paso incluida en el repositorio:
* 🇪🇸 [Manual de Usuario en Español (Markdown)](./manual_usuario_cumpa_x.md)
