**Nano Cortex Web Editor**

A browser-based editor for the Neural DSP Nano Cortex. Connects directly to your device over Bluetooth — no app install required.


Unofficial community project. Not affiliated with or endorsed by Neural DSP. Use at your own risk.



**Features**


Wireless control — connects to your Nano Cortex over Web Bluetooth (BLE)
Amp front panel — Gain, Bass, Mid, Treble, and Level knobs with real-time control
Capture & Cab/IR management — select capture slots, IR slots, mic types, and positions
Full FX editing — all Overdrive, Modulation, Delay, Reverb, Utility, Compressor, Pitch, Wah/Filter, and EQ effects with complete parameter control
Gate control — on/off toggle and reduction amount
Preset switching — change presets via Web MIDI
Save — write changes back to the current preset on the device


**Requirements**


Browser: Google Chrome or Microsoft Edge (desktop). These are currently the only browsers that support Web Bluetooth.
Device: Neural DSP Nano Cortex
Tested firmware: 2.2.1



Web Bluetooth is not available on Firefox, Safari, or mobile browsers.



**Getting Started**


Power on your Nano Cortex and make sure Bluetooth is enabled
Open the editor in Chrome or Edge
Click Connect and select your device from the Bluetooth pairing dialog
The editor will sync your current preset automatically


**How It Works**

The editor communicates with the Nano Cortex over BLE (Bluetooth Low Energy) using a reverse-engineered protocol derived from observing the official Cortex Cloud app's traffic. Preset changes are sent over Web MIDI (Program Change messages). All communication is direct between your browser and your device — nothing is sent to any server.

**Important Notes**


Back up your presets in the official Cortex Cloud app before using this editor
This is a reverse-engineered protocol — some parameters may not behave exactly as expected
Always test changes on a non-critical preset first
The editor can write to presets on the device — changes are real and persistent once saved


**Known Limitations**

Renaming of presets is not (currently) enabled
Web Bluetooth is only available in Chrome and Edge on desktop
Only one Bluetooth connection to the device at a time (disconnect from Cortex Cloud first)
Some parameter ranges may not perfectly match the official app's display values
No ability to manage Captures or Cab/IRs through the Library; use the official Cortex Cloud app


**Technical Details**

The editor is a single self-contained HTML file with no external dependencies, no build step, and no server-side component. It uses:


Web Bluetooth API for BLE communication (GATT services A002/A003, characteristics C304/C305)
Web MIDI API for preset changes
A hand-rolled protobuf wire-format parser for the device's binary protocol
All parameter index mappings verified against real BLE packet captures from the official Cortex Cloud app

The file can be downloaded and run offline if preferable


**Contributing**

Contributions are welcome. If you find a parameter that's mapped incorrectly, capturing the BLE traffic from Cortex Cloud for that specific parameter is the most useful thing you can provide — it lets us verify the exact index and value encoding the device expects.

**License**

MIT

**Disclaimer**

This project is not affiliated with, endorsed by, or connected to Neural DSP in any way. "Nano Cortex" and "Neural DSP" are trademarks of Neural DSP Technologies. This is an independent community tool built through reverse engineering of the Bluetooth protocol. Use at your own risk.
