# 🏠 Home Assistant Dashboard — Rounded-Bubble

Welcome to my custom [Home Assistant](https://www.home-assistant.io/) dashboard!  
This dashboard is designed to provide a clean, modern, and responsive experience both on mobile and desktop. It's heavily inspired by:

- 🎨 [LE0N's Rounded Dashboard](https://community.home-assistant.io/t/rounded-dashboard-guide/543043)  
- 🏡 [Damian Eickhoff's HaCasa](https://github.com/damianeickhoff/HaCasa)  
- 🫧 [Bubble Card by Clooos](https://github.com/Clooos/Bubble-Card)
- 📱 [My Smart Home](https://www.youtube.com/@My_Smart_Home)

---

## 📱 Screenshots

### 📊 Home 
<img src="https://github.com/jlnbln/My-HA-Dashboard/blob/main/images/home_desktop.png?raw=true" height="380"/> <img src="https://github.com/jlnbln/My-HA-Dashboard/blob/main/images/home_mobil.PNG?raw=true" height="380"/>

### 💡 Living Room Controls
<img src="https://github.com/jlnbln/My-HA-Dashboard/blob/main/images/room_desktop.png?raw=true" height="380"/> <img src="https://github.com/jlnbln/My-HA-Dashboard/blob/main/images/room_mobil.PNG?raw=true" height="380"/>

### 🎶 Music View
<img src="https://github.com/jlnbln/My-HA-Dashboard/blob/main/images/music_desktop.png?raw=true" height="380"/> <img src="https://github.com/jlnbln/My-HA-Dashboard/blob/main/images/music_mobil.PNG?raw=true" height="380"/>

### 💾 Server Controls
<img src="https://github.com/jlnbln/My-HA-Dashboard/blob/main/images/server_desktop.png?raw=true" height="380"/> <img src="https://github.com/jlnbln/My-HA-Dashboard/blob/main/images/server_mobil.PNG?raw=true" height="380"/>

---

## 🧩 Custom Cards Used

This dashboard combines several powerful custom components from the Home Assistant community:

- [`navbar-card`](https://github.com/joseluis9595/lovelace-navbar-card)
- [`button-card`](https://github.com/custom-cards/button-card)
- [`swipe-card`](https://github.com/bramkragten/swipe-card)
- [`decluttering-card`](https://github.com/custom-cards/decluttering-card)
- [`my-cards-bundle`](https://github.com/AnthonMS/my-cards)
- [`mini-graph-card`](https://github.com/kalkih/mini-graph-card)
- [`bubble-card`](https://github.com/Clooos/Bubble-Card)
- [`card-mod`](https://github.com/thomasloven/lovelace-card-mod)
- [`mushroom-cards`](https://github.com/piitaya/lovelace-mushroom)
- [`auto-entities`](https://github.com/thomasloven/lovelace-auto-entities)
- [`weather-card`](https://github.com/bramkragten/weather-card)
- [`kiosk-mode`](https://github.com/NemesisRE/kiosk-mode)

---

## 🧠 Features

- 📱 **Responsive Design**: Works seamlessly on mobile phones, tablets, and desktops.
- 🏠 **Room-Based Layout**: Grouped views for rooms with lighting, climate, and media control.
- 🎨 **Stylized UI**: Uses card-mod and bubble-card for a highly polished aesthetic.
- 👥 **User Specific Layout**: Dashboards adapts to which user is using it. 
- 🎶 **Music Assistant Integration**: Music Assistant directly in the dashboard and custom music player for mobile view.

---

## 🚀 Getting Started

To use this dashboard:
1. Make sure HACS is installed.
2. Install all custom cards listed above.
3. Install the rounded-bubble.yaml theme from this repository.
4. Import or adapt the YAML configuration from dashboard.yaml.
5. Customize entities and room definitions to match your setup.
6. Enjoy a clean and dynamic smart home interface!

---

## 🤖 Custom Helpers 

### Input Boolean:
Toggles Kiosk Mode to be on or off. 
<pre>
input_boolean:
  debug_rounded:
    name: Debug Rounded
    icon: mdi:view-dashboard-edit
</pre>

### Template Sensors:
Two sensors that show up in the top row of chips, which show how many lights are on and how many windows are open. 
<pre>
sensor:
  - platform: template
    sensors:
      lights_on_count:
        unique_id: lightsoncount
        friendly_name: 'Lights on count'
        value_template: >
          {% set lights_on = states.light 
            | selectattr('state', 'eq', 'on') 
            | list 
            | count %}
          {{ lights_on }}
      window_open_count:
        unique_id: windowopencount
        friendly_name: 'Window open count'
        value_template: >
          {% set windows_on = states.binary_sensor
            | selectattr('attributes.device_class', 'eq', 'window')
            | selectattr('state', 'eq', 'on')
            | list
            | count %}
          {{ windows_on }}
      
</pre>

---

## 🙌 Credits

Huge thanks to the amazing Home Assistant community and the following developers:

- [LE0N](https://community.home-assistant.io/u/LE0N)
- [Damian Eickhoff](https://github.com/damianeickhoff)
- [Clooos](https://github.com/Clooos)
- [My Smart Home](https://www.youtube.com/@My_Smart_Home)

---

## 💸 Support

If you want to hire me to make your personal dashboard you can do that [here](https://homeassistant-dashboard.com).

Or support my work through buy me a coffee.

[![BuyMeACoffee](https://raw.githubusercontent.com/pachadotdev/buymeacoffee-badges/main/bmc-yellow.svg)](https://www.buymeacoffee.com/jlnbln)


---
