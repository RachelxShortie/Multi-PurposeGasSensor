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


