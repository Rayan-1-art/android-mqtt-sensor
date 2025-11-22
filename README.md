# android-mqtt-sensor

This repo is Codespaces-ready and demonstrates an Android app that reads gyroscope/rotation vector sensor data and publishes it to an MQTT broker (HiveMQ Cloud). A web viewer subscribes to the same topic using WebSockets and renders rotation in 3D.

## Quick steps

1. Create a HiveMQ Cloud instance (free) and get the broker host, port, username, and password.
2. Open this repository in GitHub → **Code → Create Codespace on main**.
3. In Codespaces, open `android-app/app/src/main/java/com/example/mqttsensor/MainActivity.java` and fill your HiveMQ credentials.
4. Run `./gradlew assembleDebug` in the Codespace terminal.
5. Download `app/build/outputs/apk/debug/app-debug.apk` and install on your Android phone.
6. Open `web-viewer/index.html` in a browser.

