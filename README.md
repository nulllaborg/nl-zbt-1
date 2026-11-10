# NULLLAB NL-ZBT-1

**Zigbee & Thread USB Dongle**

## Overview

The NULLLAB NL-ZBT-1 is a USB wireless adapter based on the hardware design of the Home Assistant Connect ZBT-1 (formerly SkyConnect), with minor hardware refinements.

It features the same Silicon Labs EFR32MG21 wireless chipset and CP2102N USB-to-UART bridge, providing compatibility with Zigbee and Thread firmware.

The NL-ZBT-1 comes pre-flashed with official Zigbee coordinator firmware, making it ready to use with Home Assistant's Zigbee Home Automation (ZHA) integration.

## Features

- **Zigbee 3.0 Support** — Connect compatible Zigbee smart home devices.
- **Thread Support** — Supports Thread operation with compatible firmware.
- **Ready to Use** — Pre-installed official Zigbee coordinator firmware.
- **Home Assistant Compatible** — Designed for integration with Home Assistant.
- **EFR32MG21 + CP2102N** — Based on the Home Assistant Connect ZBT-1 hardware architecture.
- **Local Control** — Communicate with compatible devices without a proprietary cloud service.

## Hardware Specifications

| Parameter          | Specification                        |
| ------------------ | ------------------------------------ |
| Brand              | NULLLAB                              |
| Model              | NL-ZBT-1                             |
| Wireless Chipset   | Silicon Labs EFR32MG21               |
| USB-to-UART Bridge | Silicon Labs CP2102N                 |
| Wireless Protocols | Zigbee 3.0 / Thread                  |
| Frequency          | 2.4 GHz                              |
| USB Interface      | USB 2.0                              |
| Default Firmware   | Official Zigbee Coordinator Firmware |
| Power Supply       | 5V via USB                           |

## Getting Started

### 1. Connect the Dongle

Connect the NL-ZBT-1 to an available USB port on your Home Assistant host.

For better wireless performance, we recommend using a USB extension cable to keep the dongle away from USB 3.0 ports, external drives, and other potential sources of 2.4 GHz interference.

### 2. Set Up Zigbee in Home Assistant

The NL-ZBT-1 ships with Zigbee coordinator firmware pre-installed. No manual firmware flashing is required for initial Zigbee setup.

1. Open your Home Assistant dashboard.
2. Navigate to **Settings → Devices & services**.
3. If the dongle is automatically discovered, follow the setup instructions.
4. Otherwise, select **Add Integration** and search for **Zigbee Home Automation (ZHA)**.
5. Select the serial port associated with the NL-ZBT-1.
6. Follow the on-screen instructions to complete configuration.

If manual configuration is required, select the Silicon Labs Ember/EZSP radio type.

For more information, refer to the [Home Assistant ZHA documentation](https://www.home-assistant.io/integrations/zha/).

### 3. Pair Zigbee Devices

Once ZHA is configured:

1. Open **Settings → Devices & services**.
2. Select **Zigbee Home Automation**.
3. Click **Add device**.
4. Put your Zigbee device into pairing mode.
5. Wait for Home Assistant to discover the device.

After pairing, your device can be managed directly through Home Assistant.

## Using Thread

The NL-ZBT-1 also supports Thread operation using compatible Thread firmware.

Thread functionality has been tested on the NL-ZBT-1 hardware.

To use the dongle as a Thread radio, the pre-installed Zigbee coordinator firmware must be replaced with compatible Thread firmware.

After flashing the appropriate firmware, configure the adapter with a supported OpenThread Border Router setup.

For additional information, see:

[Home Assistant — Thread](https://www.home-assistant.io/integrations/thread/)

**Important:** Zigbee and Thread are supported through different firmware configurations. The standard firmware configuration does not provide simultaneous Zigbee and Thread operation.

## Zigbee2MQTT

The NL-ZBT-1 can also be used with Zigbee2MQTT when running supported Silicon Labs coordinator firmware.

Use the appropriate Ember adapter configuration and serial port settings for the installed firmware.

Refer to the [Zigbee2MQTT documentation](https://www.zigbee2mqtt.io/) for detailed setup instructions.

## Troubleshooting

### Dongle Not Detected

- Check the USB connection.
- Try another USB port.
- Restart Home Assistant.
- Verify that the CP2102N USB serial device is detected by the host operating system.
- If using a virtual machine or container, confirm that USB passthrough is configured correctly.

### Zigbee Devices Cannot Pair

- Make sure the device is in pairing mode.
- Move the device closer to the coordinator.
- Reset the device if it was previously paired with another Zigbee network.
- Reduce interference from nearby 2.4 GHz devices.

### Unstable Zigbee Connections

- Use a USB extension cable.
- Keep the dongle away from metal enclosures and USB equipment.
- Add mains-powered Zigbee routers to improve mesh coverage.
- Check for interference between Zigbee and Wi-Fi channels.

## Frequently Asked Questions

**Does the NL-ZBT-1 require a separate Zigbee hub?**

No. When connected to Home Assistant, the NL-ZBT-1 can operate as a Zigbee coordinator.

**Does it support Thread?**

Yes. Thread operation has been tested and verified on NL-ZBT-1 hardware. Compatible Thread firmware is required.

**Can it run Zigbee and Thread simultaneously?**

The standard configuration supports one protocol at a time. Switching between Zigbee and Thread requires changing the firmware.

**Is it compatible with Zigbee2MQTT?**

The hardware and supported Silicon Labs coordinator firmware can be used with Zigbee2MQTT. The correct firmware and adapter settings are required.

**Is the NL-ZBT-1 an official Home Assistant product?**

No. The NL-ZBT-1 is an independent product developed by NULLLAB, based on the hardware design of the Home Assistant Connect ZBT-1.

## Resources

- [Home Assistant ZHA](https://www.home-assistant.io/integrations/zha/)
- [Home Assistant Thread](https://www.home-assistant.io/integrations/thread/)
- [Home Assistant Connect ZBT-1](https://www.home-assistant.io/connectzbt1/)
- [Zigbee2MQTT](https://www.zigbee2mqtt.io/)
- [NULLLAB GitHub](https://github.com/nulllaborg)

## Support

For technical assistance or product-related questions:

**Email:** support@null-lab.com

**GitHub:** https://github.com/nulllaborg

---

*NL-ZBT-1 is an independent NULLLAB product. It is not manufactured, endorsed, or officially supported by the Open Home Foundation or Nabu Casa. Home Assistant and related trademarks belong to their respective owners.*
