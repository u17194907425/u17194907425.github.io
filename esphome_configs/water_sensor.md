# ESPHome and Water Sensor

The sensor simply returns voltage in case there's water on it

{% raw %}
```yaml

sensor:
  - platform: adc
    pin: GPIO34
    name: "Water Sensor"
    update_interval: 1s
    attenuation: 11db
    icon: "mdi:pipe-leak"
    filters:
      - or:
        - throttle: 60s # This one is to pass 0 value and not sit on ~0.07
        - delta: 0.2    # Do not spam with updates in case they are small
```
{% endraw %}
