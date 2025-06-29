# 🔎 Bluetooth Recon Project (Kali Linux + Wireshark)

## 📁 About

This project explores passive and active Bluetooth reconnaissance techniques using **Kali Linux**, focusing on identifying nearby devices, extracting service UUIDs, testing connectivity, and capturing raw data via **Wireshark**.

---

## 🎯 Objectives

- Scan and identify Bluetooth Low Energy (BLE) and Classic devices
- Extract device metadata (MAC, manufacturer, service UUIDs)
- Capture advertising packets using `btmon` and `Wireshark`
- Perform low-level pings with `l2ping`
- Analyze packet behavior and connection attempts

---

## 🛠️ Tools Used

| Tool         | Purpose                         |
|--------------|----------------------------------|
| `bluetoothctl` | Scan, pair, connect devices    |
| `btmon`       | Monitor HCI events (BLE traffic)|
| `l2ping`      | Send echo requests to devices   |
| `Wireshark`   | Capture and analyze raw packets |
| `hciconfig`   | Device interface control        |
| `maclookup.app` | Vendor identification via MAC |

---

## ⚠️ Disclaimer

This project is for **educational and ethical research purposes** only. All testing was conducted on **self-owned** or **authorized** devices in a controlled lab environment.

---

## 💡 Next Steps

- Try spoofing a BLE advertisement using `hcitool` or `bluetooth-sendto`
- Replay a packet capture
- Integrate into `Python` with `bleak` for programmatic scans
