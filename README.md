# Raspberry Pi Pico with Arduino IDE

## Blink Tutorial

A simple beginner guide to set up **Raspberry Pi Pico** with **Arduino IDE** and upload the first **Blink** program.

---

## Table of Contents

* [Requirements](#requirements)
* [Install Arduino IDE](#install-arduino-ide)
* [Add Raspberry Pi Pico Board Support](#add-raspberry-pi-pico-board-support)
* [Install the Pico Board Package](#install-the-pico-board-package)
* [Select the Board](#select-the-board)
* [Enter BOOTSEL Mode](#enter-bootsel-mode)
* [Blink Example](#blink-example)
* [Upload the Program](#upload-the-program)
* [Check the Result](#check-the-result)
* [Important Note About COM Port](#important-note-about-com-port)
* [Troubleshooting](#troubleshooting)
* [Summary](#summary)

---

## Requirements

Before starting, prepare the following:

* Raspberry Pi Pico
* USB data cable
* Arduino IDE installed on your computer

---

## Install Arduino IDE

Download and install **Arduino IDE** on your computer.

After installation, open Arduino IDE.

---

## Add Raspberry Pi Pico Board Support

In Arduino IDE:

1. Open **File > Preferences**
2. Find **Additional Boards Manager URLs**
3. Add the following URL:

```text
https://github.com/earlephilhower/arduino-pico/releases/download/global/package_rp2040_index.json
```

4. Click **OK**

---

## Install the Pico Board Package

1. Open **Tools > Board > Boards Manager**
2. Search for:

```text
pico
```

3. Install:

```text
Raspberry Pi Pico/RP2040 by Earle F. Philhower, III
```

---

## Select the Board

After the installation is complete:

1. Open **Tools > Board**
2. Select:

```text
Raspberry Pi Pico
```

---

## Enter BOOTSEL Mode

For the first upload, do the following:

1. Unplug the Pico from your computer
2. Press and hold the **BOOTSEL** button on the Pico
3. While holding the button, connect the Pico to your computer using USB
4. Release the **BOOTSEL** button

If successful, your computer will detect the Pico as a USB drive named:

```text
RPI-RP2
```

This is normal.

---

## Blink Example

Copy the following code into Arduino IDE:

```cpp
void setup() {
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop() {
  digitalWrite(LED_BUILTIN, HIGH);
  delay(500);
  digitalWrite(LED_BUILTIN, LOW);
  delay(500);
}
```

---

## Upload the Program

1. Make sure the Pico is in **BOOTSEL mode**
2. Click the **Upload** button in Arduino IDE
3. Wait until the upload process is complete

After uploading, the Pico usually restarts automatically.

If needed:

* unplug the Pico
* plug it in again **without pressing BOOTSEL**

---

## Check the Result

If the upload is successful, the built-in LED on the Pico should blink:

* ON for 0.5 seconds
* OFF for 0.5 seconds

If the LED is blinking, your setup is working correctly.

---

## Important Note About COM Port

If your Pico does **not** appear as a **COM port**, that is still okay for the first upload.

Why?

Because the first upload uses **BOOTSEL mode**, where the Pico appears as:

```text
RPI-RP2
```

and not as a serial COM port.

---

## Troubleshooting

### Pico does not appear as `RPI-RP2`

Possible causes:

* the USB cable is charging-only
* the USB port has a problem
* the Pico is not in BOOTSEL mode

Try:

* using another USB cable
* using another USB port
* repeating the BOOTSEL steps

---

### Upload fails

Check the following:

* the selected board is **Raspberry Pi Pico**
* the Pico is connected in **BOOTSEL mode**
* the board package was installed correctly

---

### LED does not blink

Check the following:

* the upload finished successfully
* the correct board was selected
* unplug and reconnect the Pico **without BOOTSEL**

---

## Summary

The basic workflow is:

1. Install Arduino IDE
2. Add the RP2040 board package URL
3. Install the Raspberry Pi Pico board package
4. Select **Raspberry Pi Pico**
5. Enter **BOOTSEL mode**
6. Upload the Blink program
7. Reconnect the Pico normally
8. Check the built-in LED

---

## Done

You have successfully uploaded your first Arduino program to the **Raspberry Pi Pico**.
