#  IoT-Based RC Boat for Real-Time Water Quality Monitoring

This project involves a remote-controlled (RC) IoT boat equipped with sensors to monitor real-time water parameters such as temperature, humidity, pH level, turbidity, and GPS location. The collected data is displayed on an OLED screen and uploaded to **ThingSpeak** for cloud-based monitoring and analysis.

##  Features

-  Real-time sensing of:
  - Temperature (°C)
  - Humidity (%)
  - pH level
  - Turbidity
  - GPS location (Latitude & Longitude)
-  Data transmitted to [ThingSpeak](https://thingspeak.com/)
-  OLED display for local visualization
-  Water quality classification & usage recommendation

##  Hardware Used

- ESP32 (NodeMCU or DevKit)
- DHT11 Temperature & Humidity Sensor
- Analog pH Sensor
- Turbidity Sensor (Analog)
- GPS Module (using SoftwareSerial)
- 0.96" OLED Display (SSD1306)
- Wi-Fi connectivity (via ESP32)
- Power supply or battery (for outdoor use)

##  Pin Configuration

| Component       | ESP32 Pin |
|----------------|-----------|
| DHT11          | GPIO 4    |
| pH Sensor      | GPIO 34   |
| Turbidity Sensor | GPIO 35 |
| GPS RX (to TX of ESP32) | GPIO 17 |
| GPS TX (to RX of ESP32) | GPIO 16 |
| OLED SDA       | Default I2C |
| OLED SCL       | Default I2C |

##  ThingSpeak Configuration

1. Create a [ThingSpeak account](https://thingspeak.com/).
2. Create a new channel and enable fields:
   - Field 1: Temperature
   - Field 2: Humidity
   - Field 3: pH
   - Field 4: Turbidity
   - Field 5: Latitude
   - Field 6: Longitude
   - Field 7: Water Quality
   - Field 8: Usage Recommendation
3. Copy your **Channel Number** and **Write API Key**.
4. Replace these values in the code:

```cpp
unsigned long myChannelNumber = YOUR_CHANNEL_NUMBER;
const char * myWriteAPIKey = "YOUR_API_KEY";
