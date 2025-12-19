
<div align="center">

# ⚡ TITAN-WEBGPU-STRESS
### The Apex of Browser Resource Exhaustion & Graphics Stack Auditing

<a href="https://github.com/DDW-X">
    <img src="https://img.shields.io/badge/POWERED_BY-DDW--X-red?style=for-the-badge&logo=github&logoColor=white" alt="DDW-X">
</a>
<a href="https://t.me/CONTROLSERVER">
    <img src="https://img.shields.io/badge/TELEGRAM-CONTROLSERVER-blue?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram">
</a>
<a href="mailto:ddw.x.dev@gmail.com">
    <img src="https://img.shields.io/badge/SUPPORT-ddw.x.dev%40gmail.com-black?style=for-the-badge&logo=gmail&logoColor=red" alt="Email">
</a>

<br><br>

[![WebGPU](https://img.shields.io/badge/API-WebGPU%20%2B%20WebGL2-success?style=flat-square&logo=opengl)](https://www.w3.org/TR/webgpu/)
[![Security Research](https://img.shields.io/badge/Category-Security%20Research-critical?style=flat-square&logo=kalilinux)](https://www.kali.org/)
[![Status](https://img.shields.io/badge/Status-ACTIVE_EXPLOIT-red?style=flat-square&animate=pulse)](https://github.com/DDW-X)
[![License](https://img.shields.io/badge/License-MIT-lightgrey?style=flat-square)](LICENSE)

</div>

---

> [!CAUTION]
> **LEGAL DISCLAIMER & WARNING**
>
> This repository contains highly potent browser stress-testing payloads (`Titan-A` and `Titan-B`). These tools rely on **Kernel-Level Graphics Driver Exhaustion** and **OOM (Out of Memory)** techniques.
>
> 1.  **DO NOT** run this on critical infrastructure or medical devices.
> 2.  **DO NOT** use this to target systems you do not own or have explicit permission to test.
> 3.  **DDW-X** assumes **NO LIABILITY** for hardware damage (thermal throttling/overheating) or data loss caused by system freezes.
>
> *This software is provided "AS IS" for educational cybersecurity research and browser vulnerability assessment.*

---

## 🏴‍☠️ Introduction

**Titan-WebGPU-Stress** is not just a benchmark; it is a weaponized auditing suite designed to expose the fragility of modern browser sandboxing. While browsers like Chrome and Edge attempt to isolate tabs, the interface between the browser and the GPU driver remains a critical attack surface.

This tool leverages **WebGPU Compute Shaders**, **Raymarching Volumetrics**, and **Parallel CPU Worker Threads** to bypass standard garbage collection and watchdog timers, forcing the host operating system into a state of non-recoverable resource starvation (DoS).

---

## 💀 Live Deployment (Click & Die)

**WARNING:** Clicking these links will immediately initiate the stress test. Save your work before proceeding.

### 🔴 Target A: ULTIMA (WebGPU + CPU)
> **Link:** [https://ddw-x-lagging-test.vercel.app](https://ddw-x-lagging-test2.vercel.app)
>
> **Description:** The bleeding edge of browser exhaustion. Combines multi-threaded CPU floating-point calculations with a heavy WebGPU Raymarching shader.
> * **Attack Vector:** CPU Core Saturation + GPU VRAM Flood.
> * **Best For:** High-end PC testing, Chrome, Edge.

### 🟠 Target B: EXTREME (WebGL2 Legacy)
> **Link:** [https://ddw-x-lagging-test2.vercel.app](https://ddw-x-lagging-test.vercel.app)
>
> **Description:** A highly optimized WebGL2 fragment shader loop designed for maximum compatibility.
> * **Attack Vector:** Pure GPU Logic Unit (ALU) saturation via nested FBM loops.
> * **Best For:** Mobile devices, older browsers, iOS Safari.

---

## 🧪 Technical Architecture & Attack Vectors

Based on the source code analysis, this suite utilizes the following vectors:

### 1. The "Gyroid" FBM Crusher (GPU ALU Saturation)
The core visual payload is a Raymarching engine rendering a Gyroid surface distorted by Fractional Brownian Motion (FBM).
* **Vector:** `Math.sin/cos/tan` heavy trigonometric abuse inside the shader.
* **Mechanism:** The shader forces the GPU to calculate light transport through volumetric fog with up to **6000 steps per pixel**.
* **Impact:** Instantly saturates 100% of GPU CUDA/Stream Cores, causing immediate desktop lag and preventing OS compositors (DWM/SurfaceFlinger) from updating the screen.

### 2. The "Thread-Burner" (CPU Core Meltdown)
The `ULTIMA` payload spawns Web Workers equal to `navigator.hardwareConcurrency`.
* **Vector:** Infinite `while(true)` loops performing floating-point chaos math (`Math.sqrt(Math.abs(x))`).
* **Mechanism:** Unlike main-thread loops, these workers cannot be blocked by UI unresponsiveness. They persist until the browser process is forcibly terminated by the OS kernel.

---

## 📊 Test Environment Report & Verified Targets

This suite has been rigorously tested by **DDW-X** in controlled environments. Below are the confirmed results:

| Target Environment | Status | Impact Level | Notes |
| :--- | :--- | :--- | :--- |
| **Google Chrome (Desktop)** | 🔴 **CRITICAL** | Total System Freeze | Mouse cursor lag, audio stuttering, TDR reset triggered after 10s. |
| **Microsoft Edge** | 🔴 **CRITICAL** | Browser Crash | Tab crashes immediately with `STATUS_ACCESS_VIOLATION` or `Out of Memory`. |
| **Telegram (Android In-App)** | 💀 **FATAL** | Device Reboot | **Confirmed:** Opening the link inside Telegram causes the phone UI to freeze, forcing a hard reboot or OS crash. |
| **Google Gemini Pro** | ⚡ **EJECTED** | **AI Session Kill** | **CRITICAL FINDING:** Pasting the source code into the Gemini Pro coding environment caused the AI's rendering environment to crash, forcing a session reload and error `RenderProcessGone`. |
| **iOS Safari (Webkit)** | 🟠 **HIGH** | Tab Reload | "A problem occurred with this webpage" loop. |

---

## 🛡️ Mitigation Strategies (For Browser Vendors)

To defend against Titan-WebGPU-Stress, vendors must implement:
1.  **Strict Shader Timeout:** Enforce harder limits on WGSL loop execution time independent of OS TDR.
2.  **Resource Quotas:** Limit total compute operations per frame in non-active tabs.
3.  **Sanitization:** Better parsing of nested FBM loops in the shader compiler to detect "infinite complexity" attacks.

---

<div align="center">

### ⚡ Powered by DDW-X
*Advancing Security Through Chaos.*

[**[ Telegram Channel ]**](https://t.me/CONTROLSERVER) • [**[ YouTube ]**](https://youtube.com/@DDW-X)

<br>
<img src="https://img.shields.io/badge/DDW--X-CERTIFIED_PAYLOAD-red?style=for-the-badge&logo=shield&logoColor=white" alt="Certified">

</div>
