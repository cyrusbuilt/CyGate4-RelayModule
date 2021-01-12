# CyGate4-RelayModule

Add-on relay module for CyGate4

## Synopsis

This is a relay add-on module for [CyGate4](https://github.com/cyrusbuilt/CyGate4).  It provides 5 addressable relays capable of switching up to 15A @ 125VAC.  This module connects to CyGate4 using the I2C (aka 2-wire) bus. It can be powered from CyGate4 itself, or from a separate 5VDC supply. Support for this module is built-in to the CyGate4 firmware. Since this relay module is based on the MCP23017, it uses a 7bit address scheme where the first 4 bits are already set and the last 3 bits are configurable via jumpers on J1 - J3. The jumpers *MUST* be set and cannot be left off.

For example, the jumper must connect the center pin and either plus (+) or or minus (-) pins. Positive (high) represents a binary 1 and negative (low) represents a binary 0.  You can have a maximum of 7 relay modules (or any other MCP23017-based devices for that matter) connected to CyGate4 at any given time. Be sure to configure that address so as not to conflict with any other devices. NOTE: Address 0 (0x20) is reserved by CyGate4 itself (all jumpers set to center and minus) and cannot be used by any other devices.

As long as the address is configured properly, the device will be auto-detected during CyGate4's boot cycle and initialized. Once initialized, the relays can be configured via CyGate4's config file or via configure/control messages sent to CyGate4 via MQTT.