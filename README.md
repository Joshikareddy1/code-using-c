# code-using-c
#include <SoftwareSerial.h>
#include <dht.h>
dht DHT
#define DHT11_PIN 7
void setup() {
Serial.begin(9600); // Enable serial monitor 
}
void loop() {    //Read data from the rain sensor  
int rainValue = analogRead(A0);
Serial.print("Rain Sensor Value= ");
Serial.println(rainValue);  //Read data from the temperature and humidity sensor (DHT11)
int chk = DHT.read11(DHT11_PIN);
Serial.print("Temperature= ");
Serial.print(int(DHT.temperature));
Serial.println(" °C");
Serial.print("Humidity= ");
Serial.print(int(DHT.humidity));
Serial.println(" %");// Read data from the soil moisture sensor
int soilMoistureValue = analogRead(A3);
Serial.print("Soil Moisture Sensor Value= ");
Serial.println(soilMoistureValue);
delay(1000); // Delay between sensor readings
} 
