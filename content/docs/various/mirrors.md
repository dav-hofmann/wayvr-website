---
title: "Mirrors"
bookIcon: "window"
description: "View-only PipeWire cast overlays for screens, regions, and windows on Wayland."
---

# Mirrors

Mirrors are overlays that show a view-only PipeWire cast of any kind; screen, region, window.

The view-only part means that mouse input will not work on these. This is due to a PipeWire protocol limitation.

Mirrors can be initialized at runtime via the keyboard taskbar's hamburger menu.

Mirrors are only supported on Wayland.

Note that not all Wayland compositors implement region / window casting.
