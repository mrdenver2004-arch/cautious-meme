#define sensorPin A0
#define relayPin 2

void setup() {
  pinMode(relayPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int moisture = analogRead(sensorPin);
  Serial.println(moisture);

  if (moisture < 500) {   // dry soil
    digitalWrite(relayPin, HIGH); // pump ON
  } else {
    digitalWrite(relayPin, LOW);  // pump OFF
  }

  delay(2000);
}# cautious-meme
