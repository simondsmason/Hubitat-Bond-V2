# Hubitat Bond V2 Integration

A comprehensive Bond Home integration for Hubitat Elevation, providing enhanced control over Bond-compatible devices with improved reliability and advanced features.

## Overview

This integration extends the original Bond Community app by Dominick Meglio with significant improvements including multi-hub support, enhanced device control, and improved reliability for one-way devices.

## Features

### 🏠 **Multi-Hub Support**
- Connect multiple Bond hubs simultaneously
- Automatic device discovery and management
- Hub-specific device naming and organization

### 🎛️ **Device Types Supported**
- **Fans** - Basic and directional fans with speed, direction, and breeze control
- **Fans with Lights** - Optional built-in light support for compatible fans
- **Motorized Shades** - Full position control with open/close/preset functionality
- **Shade Groups** - Control multiple shades as a single unit
- **Generic Devices** - Support for other Bond-compatible devices

### ⚡ **Advanced Control Features**
- **One-Way/Two-Way Communication** - Configurable for different device types
- **Command Repeat Logic** - Improved reliability for one-way devices (1-5 repeats)
- **Command Cancellation** - Prevents conflicting commands during rapid changes
- **Precise Timing** - Uses `pauseExecution` for reliable command spacing
- **State Synchronization** - Real-time device state tracking

### 💡 **Fan Light Support**
- **Automatic Detection** - Bond API automatically detects light capabilities
- **Separate Controls** - Independent fan and light control
- **Brightness Control** - Full dimming support for compatible fans
- **Migration Support** - Existing devices automatically updated

## Installation

### 1. Install the App
1. Go to **Apps** → **Hubitat Package Manager** → **Browse Apps**
2. Search for "Bond V2 Home Integration" or install via code
3. Copy and paste the **Bond Home V2 App** code

### 2. Install Device Drivers
Install the appropriate drivers for your devices:

- **Bond V2 Fan Driver** - For basic fans without direction control
- **Bond V2 Fan With Direction Driver** - For fans with direction control
- **Bond V2 Shade Driver** - For individual motorized shades
- **Bond V2 Group Shade Driver** - For shade groups

### 3. Configure Bond Hubs
1. Open the **Bond V2 Home Integration** app
2. Add your Bond hub(s) with IP address and token
3. Test the connection for each hub

### 4. Select Devices
1. Go to **Configure Devices** in the app
2. Select the devices you want to control
3. Devices will be automatically created with appropriate drivers

## Device Configuration

### Fan Configuration
- **Speed Levels** - Choose between 3-speed or 5-speed configuration
- **Communication Type** - Select One-Way or Two-Way based on your device
- **Command Repeat Count** - Set 1-5 repeats for one-way devices (default: 3)

### Shade Configuration
- **Communication Type** - Select One-Way or Two-Way based on your device
- **Command Repeat Count** - Set 1-5 repeats for one-way devices (default: 3)
- **Position Control** - Full 0-100% position control for compatible shades

## Recent Improvements (v2.05-2.10)

### 🔧 **Technical Improvements**
- **Fixed runIn Issues** - Replaced problematic `runIn` with reliable `pauseExecution`
- **Command Cancellation Logic** - Prevents conflicting commands during rapid changes
- **Enhanced Debug Logging** - Comprehensive logging for troubleshooting
- **Improved State Management** - Better device state tracking and synchronization

### 🎯 **Reliability Enhancements**
- **One-Way Device Support** - Improved reliability for devices without state feedback
- **Command Repeat Logic** - Configurable repeat counts for better device control
- **Conflict Prevention** - Smart command cancellation prevents device conflicts
- **Precise Timing** - 500ms spacing between repeated commands

### 🏗️ **Architecture Improvements**
- **Consistent Driver Structure** - All drivers now follow the same patterns
- **Enhanced Error Handling** - Better error recovery and logging
- **State Persistence** - Improved state management across driver updates
- **Migration Support** - Automatic updates for existing devices

## Troubleshooting

### Light Support Issues
If fan lights aren't working:
1. Check the device's `hasLight` attribute in Hubitat
2. Run the migration command: `migrateDevicesForLightSupport()`
3. Re-configure devices in the Bond V2 app

### Command Repeat Issues
If commands aren't repeating properly:
1. Check the device's Communication Type setting
2. Verify the Command Repeat Count is set appropriately
3. Check Hubitat logs for any error messages

### Connection Issues
If devices aren't responding:
1. Verify Bond hub IP address and token
2. Check network connectivity to Bond hub
3. Test connection in the Bond V2 app

## Version History

### V2.10 (2025-01-01)
- Fixed runIn issues by switching to pauseExecution
- Added command cancellation logic
- Added communication preferences to Fan With Direction Driver
- Improved one-way device reliability

### V2.09 (2025-01-01)
- Added One-Way/Two-Way communication preference
- Added command repeat functionality
- Enhanced device reliability

### V2.08 (2025-07-03)
- Fixed light capability implementation
- Separated fan/light controls
- Added optional light support for fans

### V2.07 (2025-07-03)
- Added optional light support for fans with built-in lights
- Enhanced device naming with hub identification

### V2.06 (2025-07-03)
- Changed device naming to include hub identification
- Automatic migration of existing devices

### V2.00-2.05 (2025-01-01)
- Initial V2 version with multi-hub support
- Enhanced setPosition for shades
- Bond groups support
- Improved state tracking and synchronization

## Credits

- **Original Work** - Dominick Meglio (Bond Community app)
- **V2 Enhancements** - Simon Mason
- **Community Contributions** - Various Hubitat community members

## Support

For issues and questions:
1. Check the troubleshooting section above
2. Review Hubitat logs for error messages
3. Verify Bond hub connectivity and configuration
4. Check device-specific settings and preferences

---

**Note:** This integration is designed for Bond-compatible devices. Ensure your devices are compatible with the Bond hub before installation.
