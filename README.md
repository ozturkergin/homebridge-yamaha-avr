<img src="branding/yamaha_homebridge.png" width="500px">

# homebridge-yamaha-avr

[Homebridge](https://github.com/homebridge/homebridge) plugin for Yamaha Audio Receivers.
Based on the original work by [nitaybz](https://github.com/nitaybz) and the [averkiev fork](https://github.com/averkiev/homebridge-yamaha-receiver-ya).

<img src="branding/product.png" width="300">

### 🚀 Features

- **Power Control**: Turn your receiver on/off from HomeKit.
- **Volume Control**: Control volume using a Lightbulb or Fan slider for precise adjustment.
- **Input Selection**: Switch between HDMI, AV, Tuner, and other inputs.
- **Multi-Zone Support**: Independently control Zone 2, Zone 3, and Zone 4.
- **Custom Volume Ranges**: Set minimum and maximum volume levels for each zone.
- **Auto-Discovery**: Automatically find supported receivers on your network.

### 📋 Requirements

<img src="https://img.shields.io/badge/node-%3E%3D20.0.0-brightgreen"> &nbsp;
<img src="https://img.shields.io/badge/homebridge-%3E%3D1.11.1-brightgreen">

- [x] Set static IP for the receiver
- [x] Turn on "Network Stand-By" in the receiver settings
- [x] Check Node Version with `node -v`
- [x] Check Homebridge version with `homebridge -V`

### 🛠️ Installation

#### One-line Installation for Raspberry Pi (SSH)
If you are running Homebridge as a service (hb-service) on Raspberry Pi or Linux, you can install the plugin directly with this command:

```bash
sudo hb-service add https://raw.githubusercontent.com/ozturkergin/homebridge-yamaha-avr/master/homebridge-yamaha-avr-ergin-1.0.2.tgz
```

#### Manual Installation
1. Download the latest `.tgz` release from GitHub.
2. Install the plugin using: `npm install -g ./homebridge-yamaha-avr-ergin-1.0.2.tgz`
3. Update your `config.json` file (see example below).

### ⚙️ Configuration Example

```json
{
  "platforms": [
    {
      "platform": "YamahaReceiver",
      "discovery": true,
      "statePollingInterval": 10,
      "receivers": [
        {
          "name": "Living Room Receiver",
          "ip": "192.168.1.15",
          "minVolume": -80,
          "maxVolume": 10,
          "volumeAccessory": "bulb"
        },
        {
          "name": "Multi-Zone Setup",
          "ip": "192.168.1.16",
          "enableZone2": true,
          "zone2MinVolume": -60,
          "zone2MaxVolume": 10
        }
      ]
    }
  ]
}
```

### 🔗 Repositories

<table border="0">
  <tr>
    <td align="center">
      <a href="https://github.com/ozturkergin/homebridge-yamaha-avr">
        <img src="branding/github.svg" width="48px" alt="GitHub" /><br />
        <b>GitHub</b>
      </a>
    </td>
  </tr>
</table>

---
*Fork by @averkiev. Created by @nitaybz. Maintained by @ozturkergin.*
