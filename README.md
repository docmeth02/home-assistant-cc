# Comet Blue thermostats

 - reads beacons sent out by devices to find out about current state, thus no polling
 - active connection is only made to change settings
 - MQTT bridge automatically retries BTLE connections
 - indicates connection failures/no beacons using icon
 - sets correct time/date and desired PIN if not already set

__Working features:__
 - set desired temp
 - show measured and target temp
 - apply offset to measured temp (should be the same you set on the device) per device in config file
 - read battery level (show using icon)
 - set mode (auto, manual, manual_locked, auto_locked)

Also possible, but not implemented, partially because no HA support:
 - set timer plan
 - detect "window open" state
 - set warm/cold temperature


Example device configuration.yaml block:
```yaml
climate:
  - platform: sygonix
    devices:
      'Living Room':
        mac: 'AA:BB:CC:DD:EE:FF'
        pin: 000000
        offset: -1.5
```
