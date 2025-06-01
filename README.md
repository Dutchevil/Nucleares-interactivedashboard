# 🚀 Nucleares Dynamic Dashboard 💡

> **Welcome to the most electrifying, blinking‐alive SVG dashboard on GitHub!**  
> Monitor pumps, valves, and turbines in **real time** with colors, emojis, and pulses! 🔥

---

## 🎯 Overview

The **Nucleares Dynamic Dashboard** is a FULL-SCREEN, INTERACTIVE SVG-based web page that shows your entire plant layout—**pumps**, **valves**, **turbines**, and more—**LIVE** ⚡.  
Every second, it polls a local data server, updates colors, blinks alarms, and keeps you on top of your system’s health! 🚨

---

## ✨ Key Features

- 🖼️ **Full-Screen SVG**  
  - An inline `<svg id="myplant">` spans the entire viewport—zoom & pan anywhere to see every detail! 🔍

- 🔄 **Real-Time Polling (1 sec interval)**  
  - Uses `fetch('http://localhost:8785/?variable=<NAME>')` to retrieve live values.  
  - Accepts plain `"true"`, `"false"`, or numeric strings like `"47.2"`.  
  - Magically updates every second—no manual refresh needed! ⏱️

- 🎨 **Dynamic Color Coding**  
  - **⚫ Black** = Pump/Component NOT INSTALLED  
  - **🟢 Lime-Green** = Normal Operation  
  - **⚠️ Orange** = Maintenance Alert (speed deviates ≥ 2%)  
  - **🔴 Red** = Overload Alarm (and it BLINKS!)  
  - **⚪ Gray** = Inactive/Off  
  - **🟡 Yellow** = Partial/Intermediate State  
  - Colors pop behind each pump or valve so you instantly know what’s happening! 🌈

- 🚨 **Blinking Alarms**  
  - Overloaded pumps/valves get a pulsing, **“blink‐blink”** CSS animation.  
  - Your eyes immediately catch any 🚨critical🚨 condition!  

- 🖱️ **SVG Pan & Zoom**  
  - Integrated [svg-pan-zoom v3.6.1](https://github.com/svg-pan-zoom/svg-pan-zoom) for smooth navigation.  
  - Inverted scroll: **scroll-down to ZOOM IN**, scroll-up to zoom out (just the way you like it!).  
  - Drag-and-drop panning—move around your plant with ease.  

- ✏️ **Live Label Updates**  
  - Each pump/valve has a text label (e.g. `Pump: 75%`, `MSCV: 40%`).  
  - The script rewrites `.textContent` every cycle—no stale numbers! 📊
