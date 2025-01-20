# Multi-PurposeGasSensor
The MQ-135 is a gas sensor, specifically designed to detect a range of air pollutants. It’s part of the MQ series, produced by the Chinese company Hanwei Electronics. The MQ sensors are widely used in various air quality monitoring applications, including home air quality systems, industrial monitoring, and environmental research.

## Key Features:
Detection Range: The MQ-135 is designed to detect a variety of gases, including ammonia (NH3), nitrogen oxides (NOx), alcohol, benzene, smoke, and carbon dioxide (CO2), among others.
## Sensor Type: 
It's a solid-state sensor that uses a heating element and a metal oxide semiconductor (MOX) layer. The heating element warms the semiconductor, allowing it to interact with gases in the air, changing the resistance based on the presence of specific gases.
## Sensitivity: 
The sensor’s resistance changes depending on the concentration of the gases in the air, and this change is used to measure the concentration of the target gas.
## Technical Specifications:
## Voltage: 
The sensor typically operates at 5V DC.
## Output: 
It offers both an analog output (which varies with gas concentration) and a digital output (which is typically used to indicate a threshold level of a particular gas).
## Heater Resistance: 
31Ω (depending on the model).
## Preheating Time: 
Around 24 to 48 hours for calibration.
# Applications:
## Air Quality Monitoring: 
The MQ-135 is often used in air quality monitors to assess pollution levels, particularly in urban environments or industrial areas.
## Air Purifiers: 
Used in some air purifiers to monitor air quality and adjust filtration rates accordingly.
## Indoor Air Quality (IAQ) Systems: 
It can be integrated into smart home systems to monitor and control indoor air quality.
Environmental Testing: Useful in testing for hazardous gases in various environments, including factories and chemical plants.
## Calibration:
The sensor needs to be calibrated in a fresh air environment to ensure accurate readings. Calibration is important because the sensor's resistance can vary with environmental conditions, such as humidity and temperature.

## Limitations:
## Cross-sensitivity: 
The MQ-135 is sensitive to a wide range of gases, but this can also lead to interference from other gases. For example, it may give false readings in environments with high concentrations of multiple gases.
## Long Warm-up Time: 
The sensor needs a warm-up period before it gives accurate readings.
## Lifespan: 
Over time, the sensor can degrade, so it's important to replace it as part of routine maintenance.
## Conclusion:
The MQ-135 is a versatile and cost-effective gas sensor commonly used for detecting air pollutants. It is a popular choice in environmental monitoring, air quality testing, and smart home systems. However, its cross-sensitivity and need for calibration can be challenges that users need to manage carefully.


# Project Code
// Define the pins for the MQ-135 sensor and the LED
#define MQ135_PIN A0  // Analog pin for MQ-135 output
#define LED_PIN 2     // LED pin

void setup() {
  // Start serial communication for debugging
  Serial.begin(9600);

  // Set the LED pin as OUTPUT
  pinMode(LED_PIN, OUTPUT);
}

void loop() {
  // Read the analog value from the MQ-135 sensor (0-1023 range)
  int sensorValue = analogRead(MQ135_PIN);

  // Print the sensor value to the Serial Monitor for debugging
  Serial.print("Sensor Value: ");
  Serial.println(sensorValue);

  // Control the LED based on the sensor value
  if (sensorValue < 330) {  // Good air quality
    digitalWrite(LED_PIN, LOW);  // Turn OFF the LED
    Serial.println("Good air quality: LED OFF");
  }
  else {  // Poor air quality
    digitalWrite(LED_PIN, HIGH); // Turn ON the LED
    Serial.println("Poor air quality: LED ON");
  }

  delay(1000);  // Wait for 1 second before the next reading
}


## Gases The Sensor Can Detect: 
The MQ-135 Gas Sensor can identify dangerous gases and smoke, including ammonia (NH3), sulfur (S), benzene (C6H6), and CO2. This MQ135 sensor, like the others in the MQ series of gas sensors, has a pin for both digital and analog output.

1. Components Needed:
- MQ-135 Gas Sensor
- Arduino Board (e.g., Arduino Uno, Nano, etc.)
- Jumper wires
- Breadboard (optional, but helpful)

2. Pinout of the MQ-135 Sensor:
The MQ-135 sensor has 4 pins:
VCC (Pin 1): Power supply (5V).
GND (Pin 2): Ground.
AOUT (Pin 3): Analog output (provides a varying voltage depending on gas concentration).
DOUT (Pin 4): Digital output (gives a binary signal, HIGH or LOW, based on a set threshold).

4. Wiring the MQ-135 Sensor to Arduino:
For Analog Output (AOUT):
VCC → 5V on Arduino
GND → GND on Arduino
AOUT → A0 (analog input pin) on Arduino
DOUT → Leave unconnected or connect to a digital pin to use the digital output.

For Digital Output (DOUT):
VCC → 5V on Arduino
GND → GND on Arduino
AOUT → Unconnected (if using digital output only)
DOUT → D2 (or any available digital pin on Arduino)

6. Powering the Sensor:
The MQ-135 works with a 5V power supply, which you can provide directly from the 5V pin on the Arduino. However, during operation, the sensor's heater may cause it to draw significant current, especially when warming up. It’s a good practice to allow it to warm up for 24-48 hours in clean air for stable readings.

7. Arduino Code to Read MQ-135 Sensor:
Now that the sensor is connected, add an Arduino program to read the data from the sensor.

# Boolean Logic in the Code:
To use Boolean logic with the MQ-135 gas sensor on an Arduino, you'll typically rely on the digital output (DOUT) to determine whether the gas concentration exceeds a certain threshold. You can then use Boolean logic to trigger actions like turning on alarms, controlling fans, or activating air purifiers.

Boolean logic involves using TRUE (1) and FALSE (0) to make decisions.
The digital output (DOUT) from the MQ-135 is either HIGH (1) or LOW (0), depending on whether the gas concentration exceeds a predefined threshold.

If the gas concentration exceeds the threshold, the digital output (DOUT) will be HIGH (1), and you can perform an action.
If the gas concentration is below the threshold, the digital output (DOUT) will be LOW (0), and you can perform a different action.
Steps to Use Boolean Logic with MQ-135:
Set the Digital Pin for DOUT: The digital output (DOUT) will be connected to a digital pin on your Arduino, and you’ll read this pin to check whether the gas concentration exceeds the threshold.

Define the Actions: Based on the state of the digital output (either HIGH or LOW), use Boolean logic to control actions like triggering alarms or controlling devices.

Serial.println(): Prints messages to the Serial Monitor for debugging and viewing the status of gas concentration.

# Progress Throughout Project Link To Docs:
https://docs.google.com/document/d/1ycSrD5aEMXP8b4iOWRAaYxe6nc4VWNXuJbO2A38YOls/edit?tab=t.0 





