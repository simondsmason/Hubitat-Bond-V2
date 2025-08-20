# Bond V2 Integration - File Locations Quick Reference

## Main Application Files

### **Bond Home V2 App**
- **File:** `Bond Home V2 App`
- **Purpose:** Main Hubitat app that manages Bond hub connections and device creation
- **Key Features:**
  - Multi-hub support
  - Device discovery and management
  - State synchronization
  - API communication with Bond hubs
- **Hubitat Location:** Apps → Hubitat Package Manager → Browse Apps

### **Device Drivers**

#### **Bond V2 Fan Driver**
- **File:** `Bond V2 Fan Driver`
- **Purpose:** Controls basic fans without direction control
- **Capabilities:** FanControl, Switch, SwitchLevel, Light
- **Hubitat Location:** Drivers → Hubitat Package Manager → Browse Drivers

#### **Bond V2 Fan With Direction Driver**
- **File:** `Bond V2 Fan With Direction Driver`
- **Purpose:** Controls fans with direction control capability
- **Capabilities:** FanControl, Switch, SwitchLevel, Light + Direction
- **Hubitat Location:** Drivers → Hubitat Package Manager → Browse Drivers

#### **Bond V2 Shade Driver**
- **File:** `Bond V2 Shade Driver`
- **Purpose:** Controls individual motorized shades
- **Capabilities:** WindowShade, Switch, Refresh
- **Hubitat Location:** Drivers → Hubitat Package Manager → Browse Drivers

#### **Bond V2 Group Shade Driver**
- **File:** `Bond V2 Group Shade Driver`
- **Purpose:** Controls groups of motorized shades as a single unit
- **Capabilities:** WindowShade, Switch, Refresh
- **Hubitat Location:** Drivers → Hubitat Package Manager → Browse Drivers

## Documentation Files

### **README.md**
- **File:** `README.md`
- **Purpose:** Main documentation with installation instructions and feature overview
- **Contains:** Installation guide, features, troubleshooting, version history

### **FILE_LOCATIONS.md** (This File)
- **File:** `FILE_LOCATIONS.md`
- **Purpose:** Quick reference for finding files in this repository
- **Contains:** File locations, purposes, and Hubitat installation locations

## Key API Endpoints Used

### **Bond API Documentation**
- **Primary:** https://docs.bondhome.io/
- **Website:** https://bondhome.io/
- **Support:** https://bondhome.io/support/

### **Main API Endpoints**
- **System Version:** `GET /v2/sys/version`
- **Devices:** `GET /v2/devices`
- **Device State:** `GET /v2/devices/{id}/state`
- **Device Actions:** `PUT /v2/devices/{id}/actions/{action}`
- **Groups:** `GET /v2/groups`
- **Group Actions:** `PUT /v2/groups/{id}/actions/{action}`

## Installation Order

1. **Bond Home V2 App** (Main app)
2. **Device Drivers** (Choose based on your devices):
   - Basic fans → Bond V2 Fan Driver
   - Directional fans → Bond V2 Fan With Direction Driver
   - Individual shades → Bond V2 Shade Driver
   - Shade groups → Bond V2 Group Shade Driver

## Recent Updates

### **Version 2.12 (2025-08-20)**
- Fixed light state overriding main switch state
- Main switch now correctly represents fan power state

### **Version 2.11 (2025-07-19)**
- Fixed fan state synchronization issue
- Speed now shows "off" when fan is powered off

## Troubleshooting Quick Links

- **Light Support Issues:** Check `hasLight` attribute, run migration command
- **Command Repeat Issues:** Check Communication Type and Repeat Count settings
- **Connection Issues:** Verify Bond hub IP and token
- **State Conflicts:** Check device logs for conflicting state updates

---
*Last Updated: 2025-08-20*
*Repository: https://github.com/simonmason/hubitat-bond-v2*
