# RoverArm Control

Public static dashboard for the ESP32 5-axis robotic arm and 4-wheel rover.

## Publish with GitHub Pages

1. Open **Settings → Pages** in this repository.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch **main** and folder **/(root)**, then Save.
4. Wait for the Pages deployment to finish. The public site will be:
   https://mathewsangel841-spec.github.io/roverarm-control/

## Local use

Open the page through HTTPS (GitHub Pages) or localhost. Camera permissions require a secure context. For local ESP32 hotspot operation, connect your laptop to the ESP32 Wi-Fi and use the dashboard WebSocket URL `ws://192.168.4.1:81/`.

## Important security and connectivity notes

- This repository contains the public dashboard only. Do not commit Wi-Fi passwords, pairing tokens, or private firmware settings.
- The current ESP32 firmware uses a local, non-TLS WebSocket endpoint. Modern browsers may block a public HTTPS page from connecting to `ws://` due to mixed-content restrictions. For local use, serve the dashboard from localhost on the laptop, or implement a secure WSS relay / TLS endpoint for remote control.
- Keep the robot physically supervised, test with wheels lifted, and use the emergency stop. Never expose an unauthenticated motor-control endpoint to the public internet.
- Battery voltage display requires a correctly wired and calibrated voltage divider. Never allow more than 3.3 V at an ESP32 ADC pin.
- Webcam video is processed locally by the browser; it is not uploaded to GitHub Pages.
