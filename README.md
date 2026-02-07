# IR-Safety-Vision-Prototype-v1.0
This repository contains a Python-based computer vision prototype designed to solve the problem of "alert fatigue" in industrial environments. By combining spatial zone mapping with Near-Infrared (NIR) signal simulation, the system provides a context-aware safety layer that only triggers alerts when unequipped personnel enter high-risk areas.


The prototype operates on a dual-condition validation architecture to eliminate the false alarms that plague traditional motion-based safety cameras.

-Spatial Filtering (Context): Instead of monitoring the entire frame, the system first verifies if a detected "Person" object intersects with a pre-defined High-Risk Polygon. If the worker is in a "Green Zone" (breakroom, walkway), the system remains idle.

-Signature Extraction (Compliance): Once inside a "Red Zone," the system switches to Luminance Thresholding. It scans the upper torso and head area for concentrated pixel clusters that exceed 90% brightness—simulating the retroreflective return of an IR-illuminated     safety vest.

-The Trigger: An alert is generated only if:
Worker_Position == INSIDE_DANGER_ZONE AND * Reflective_Signature == NOT_DETECTED
