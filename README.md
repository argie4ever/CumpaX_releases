<p align="center">
  <img width="240" height="240" alt="CumpaX_logo" src="https://github.com/user-attachments/assets/6c88ae87-6aca-4bf4-8b60-abb7ddd62d08" />
</p>


# Cumpa X

[![Release](https://img.shields.io/badge/Release-v1.5.0-blue?style=for-the-badge)](https://github.com/arielledesmabecerra/Cumpa_X_Releases/releases/latest)
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

**Cumpa X** es una suite de automatización, conforming e interoperabilidad para **Apple Final Cut Pro (FCPX)**. Resuelve los cuellos de botella más críticos de la línea de tiempo magnética al tender puentes directos hacia suites de corrección de color (**DaVinci Resolve**), mezcla de sonido profesional (**Avid Pro Tools**) y entornos de efectos visuales (**OpenTimelineIO**), eliminando la dependencia histórica de utilidades de terceros.

### 🚀 Módulos y Funcionalidades Principales

#### 1. Exportación AAF Nativa para Avid Pro Tools (`UniversalExportView`)
* **Serialización Binaria CFBF v3:** Generación directa de contenedores AAF estándar (SMPTE ST 2001-1 / AMWA AS-01) en memoria, sin software puente adicional.
* **Descenso Cartesiano de Pistas:** Convierte la jerarquía magnética de FCPX en pistas continuas de audio mapeando roles y sub-roles (`Dialogue`, `Effects`, `Music`, `LAV1`, `Boom`) como pistas mono o pares estéreo.
* **3 Modalidades de Medios:**
  * **Vinculado (*Linked*):** Referencia directa a los archivos Broadcast Wave / WAV en disco preservando metadatos iXML y BEXT.
  * **Consolidado a Carpeta con Manijas (*Consolidated with Handles*):** Recorta y copia los segmentos de audio necesarios con colas de edición configurables (12, 24, 48 frames).
  * **Embebido (*Embedded*):** Integra los flujos PCM de audio directamente dentro del contenedor binario AAF.
* **Informe de Entrega (`ConversionReport`):** Emite una guía técnica estructurada en Markdown para el ingeniero de mezcla con el desglose de pistas, duraciones racionales y pasos de importación.

#### 2. Interoperabilidad Bidireccional OpenTimelineIO (`.otio`)
* **Importación Nativa a FCPXML (`OTIOParser`):** Asimila secuencias `.otio` provenientes de DaVinci Resolve, Blender o herramientas VFX, convirtiéndolas en proyectos magnéticos FCPXML 1.10.
* **Exportación Nativa (`OTIOSerializer`):** Genera esquemas canónicos ASWF con intercalado matemático de `Gap.1` para garantizar la continuidad temporal exacta requerida en conforming y composición.

#### 3. Exportador a Pistas Tradicionales (`XMEML v4`)
* Convierte secuencias magnéticas de FCPXML 1.10 a líneas de tiempo tradicionales cartesianas compatibles con Adobe Premiere Pro, DaVinci Resolve y Final Cut Pro 7.
* Asigna la historia principal a `V1`, clips conectados a pistas superiores (`V2`, `V3`...) y audios a canales independientes (`A1`, `A2`...).
* Conserva reencuadres (*Basic Motion*: escala, rotación, posición), niveles de audio en dB, paneo estéreo, metadatos de rodaje (escena, toma, rollo) y marcadores.
* **Supresión Inteligente de Audio Scratch:** Identifica y silencia automáticamente el audio de referencia de cámara cuando existen pistas de sonido directo dedicadas.

#### 4. Aplanado Multicámara Avanzado (*Flatten Multicam*)
* Sustituye contenedores `<mc-clip>` por cortes directos independientes en la línea de tiempo principal.
* **Aplanado Autónomo:** Permite aplanar clips multicámara directamente desde el navegador de eventos sin necesidad de un proyecto previo.
* **Modo Pistas Apiladas (*Explode All Angles*):** Apila todos los ángulos sincronizados en carriles paralelos (`V1`, `V2`, `V3`...) para revisión multi-ángulo.
* **Pista de Referencia A/B:** Inserta una pista superior de verificación para comprobar cortes cuadro a cuadro con la tecla `V`.
* **Desempaquetado y Consolidación de Audio:** Resuelve clips sincronizados (`<sync-clip>`) mapeando micrófonos discretos (LAVs, Boom) a sus archivos reales sin generar micro-cortes.

#### 5. Transcripciones y Minutados Automatizados
* Procesa minutados y transcripciones estructuradas en texto plano o Markdown (`.txt`, `.md`).
* Genera colecciones de **Palabras Clave (Keywords)** por rango sobre clips y multicámaras en el navegador de FCPX.
* Ensambla secuencias de **Primer Corte (Rough Cuts)** en la historia principal con títulos temáticos y marcadores de diálogo.
* Detección matemática automática del framerate del proyecto base para sincronía sub-frame.

#### 6. Integración y Conectividad FCPX en 1 Clic
* **Captura Directa ("Traer de FCPX"):** Exportación e importación temporal en segundo plano automatizada mediante AppleScript y `/tmp`.
* **Inyección en 1 Clic ("Abrir en Final Cut Pro"):** Despacha el FCPXML generado directamente a FCPX sin pasos manuales en el Finder.
* **Pre-validador DTD 1.10 en Tiempo Real:** Inspecciona el árbol XML completo antes del despacho, certificando Doctype oficial, aritmética temporal racional exacta (`value/timescale s`) e integridad de recursos.

### Requisitos del Sistema
* **Sistema Operativo:** macOS 14.0 (Sonoma) o superior.
* **Apple Final Cut Pro:** Versión 10.6 o superior.
* **Arquitectura:** Binario universal nativo para **Apple Silicon (M1/M2/M3/M4)** y procesadores **Intel**.

### Instalación
1. Descarga el instalador `Cumpa_X_1.5.0_macOS.zip` desde los enlaces inferiores o la sección de [Releases](https://github.com/arielledesmabecerra/Cumpa_X_Releases/releases/latest).
2. Arrastra `Cumpa X.app` a tu carpeta de **Aplicaciones**.
3. **Primera ejecución:** Haz clic derecho (o `Control + Clic`) sobre la aplicación y selecciona **Abrir** para confirmar la excepción de seguridad de macOS.

---

## 🇺🇸 Overview

**Cumpa X** is a specialized automation, conforming, and interoperability suite for **Apple Final Cut Pro (FCPX)**. It addresses native magnetic timeline bottlenecks by establishing high-fidelity export and import bridges to color grading (**DaVinci Resolve**), professional audio mixing (**Avid Pro Tools**), and visual effects pipelines (**OpenTimelineIO**).

### 🚀 Key Modules & Capabilities

* **Native AAF Export for Avid Pro Tools:**
  * Direct binary OLE Compound File (CFBF v3) generation adhering to SMPTE ST 2001-1 and AMWA AS-01 specifications.
  * Deconstructs magnetic audio layouts into continuous session tracks based on FCPX roles (`Dialogue`, `Effects`, `Music`, `LAV1`, `Boom`).
  * Supports *Linked*, *Consolidated with Handles* (12, 24, 48 frames), and *Embedded* media modes.
  * Emits an automated Markdown sound turnover report for audio engineers.
* **Bidirectional OpenTimelineIO (`.otio`):**
  * Native ingest of external `.otio` sequences into FCPXML 1.10 projects.
  * Native export with continuous rational `Gap.1` interleaving to preserve timing integrity across Resolve and VFX tools.
* **Traditional Track Exporter (`XMEML v4`):**
  * Converts FCPXML magnetic storylines into traditional Cartesian multi-track timelines for Adobe Premiere Pro and DaVinci Resolve.
  * Preserves scale, rotation, positioning, audio volume levels, stereo pan, shooting metadata (scene, take, reel), and markers.
* **Advanced Multicam Flattening:**
  * Unwraps `<mc-clip>` multicam containers into discrete timeline cuts.
  * Supports flattening standalone multicam clips directly from the Event Browser.
  * Offers an *Explode All Angles* mode to stack synchronized cameras on parallel video tracks (`V1`, `V2`, `V3`...).
  * Includes an A/B reference lane (toggle with key `V`) and deep audio unbundling to prevent cross-track micro-cuts.
* **Script & Timecode Ingestion:**
  * Converts plain text or Markdown timecoded transcripts (`.txt`, `.md`) into range-based Keywords and auto-assembled Rough Cut sequences.
* **Direct FCPX Workflow Integration:**
  * 1-Click *Fetch from FCPX* and *Open in Final Cut Pro* via automated Apple Events.
  * Real-time Apple FCPXML DTD 1.10 pre-validation engine.

### System Requirements
* **Operating System:** macOS 14.0 (Sonoma) or higher.
* **Apple Final Cut Pro:** Version 10.6 or higher.
* **Architecture:** Universal binary (Native Apple Silicon M1/M2/M3/M4 & Intel 64-bit).

---

## 📦 Descargas / Direct Downloads

| Plataforma | Archivo | Arquitectura |
| :--- | :--- | :--- |
| **macOS** | [**`Cumpa_X_v1.5.0_macOS.zip`**](https://github.com/argie4ever/CumpaX_releases/releases/download/v1.5.0/Cumpa_X_v1.5.0_macOS.zip) | Apple Silicon & Intel (Universal) |

---

## 📖 Documentación / Documentation

Consulta la guía operativa completa paso a paso incluida en el repositorio:
* 🇪🇸 [Manual de Usuario en Español (Markdown)](https://github.com/argie4ever/CumpaX_releases/releases/download/v1.5.0/manual_usuario_cumpa_x.md)
