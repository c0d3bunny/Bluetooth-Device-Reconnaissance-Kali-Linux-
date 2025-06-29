Project: Bluetooth Device Reconnaissance (Kali Linux)
Author: Tina
Status: ✅ Working prototype

🧊 Tools Used:
~ bluetoothctl
~ btmon
~ l2ping
~ hcitool (deprecated but tested)
~ Wireshark
~ maclookup.app

🧊 Objective
To detect, identify, and interact with Bluetooth Low Energy (BLE) devices in range using Linux tools. This includes identifying iPhones, IoT sensors, and estimating proximity via RSSI and latency.

1. **Device Discovery**
   
bluetoothctl
power on
agent on
scan on

✅ Result: Devices appeared with NEW, CHG, DEL flags.

{MY}’s iPhone showed up as:

Device 0C:XX:XX:XX:XX:8B
Name: {MY}’s iPhone
Paired: no
Trusted: no
Connected: no

📡 **Bluetooth Ping (l2ping)**
Tool used: l2ping — part of BlueZ suite
Purpose: Measures round-trip time (RTT) between Kali and a Bluetooth device (similar to ping for IP)

Command Used: sudo l2ping 0C:XX:XX:XX:XX:8B
🧾 Output Example:
Ping: 0C:XX:XX:XX:XX:8B from 08:BF:XX:XX:XX:30 (data size 44) ...
0 bytes from 0C:85:E1:27:06:8B id 0 time 17.71ms
0 bytes from 0C:85:E1:27:06:8B id 1 time 34.35ms
...
📌 Interpretation:
The iPhone responds to low-level pings, confirming it is alive and discoverable.

**🧬 Wireshark Bluetooth Capture**
Tool used: Wireshark
File generated: /tmp/wireshark_bluetoothXXXXXX.pcapng

Filter used: bthci_evt || bthci_cmd || btcommon (optional)

Captured HCI events, advertisements, and UUID info

🔎 What We Observed:
LE Advertising Packets from Telink (IoT) and Apple (iPhone)
ADV_IND and ADV_NONCONN_IND packets from BLE devices

Manufacturer-specific Data:
Xiaomi Inc. UUID 0xfe95
Apple Inc. (type 0x4c00) with metadata bytes

Detected UUIDs like:
Audio Gateway
Phonebook Access
Message Access Server

🧬 Bluetooth Layer Breakdown (in Wireshark):

HCI H4	Host Controller Interface (raw comms)
L2CAP	Logical Link Control (channels & services)
ATT/GATT	Attribute Protocol & Generic Attribute Profile
SM (Security)	Handles pairing, encryption, etc.


