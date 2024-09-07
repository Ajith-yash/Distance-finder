Distance finder

components required

arduino uno R3

ultrasonic sensor

jumper wire(male to female 4)

arduino ide(software to upload program to arduino)

printer cable 

connection is available as the file 

now open Arduino IDE on your laptop

now connect your Arduino and the laptop using the cable

now upload the code

#define trigPin 5 // Define trigger pin for the sensor

#define echoPin 6  // Define echo pin for the sensor

long duration; // Variable to store pulse duration

int distance;  // Variable to store the calculated distance

void setup() {
  
  pinMode(trigPin, OUTPUT);  // Set trigger pin as output
  
  pinMode(echoPin, INPUT);    // Set echo pin as input
  
  Serial.begin(9600);        // Start serial communication at 9600 baud rate

}


void loop() {

  digitalWrite(trigPin, LOW);    // Set trigger pin LOW for stability
  
  delayMicroseconds(2);           // Wait for 2 microseconds

  
  digitalWrite(trigPin, HIGH);   // Set trigger pin HIGH for 10 microseconds
  
  delayMicroseconds(10);
  
  digitalWrite(trigPin, LOW);    // Set trigger pin LOW again

  duration = pulseIn(echoPin, HIGH);  // Measure pulse duration in microseconds

  // Calculate distance in centimeters (speed of sound is 340 m/s)
  
  distance = duration * 0.034 / 2;
  
  Serial.print("Distance: ");
  
  Serial.print(distance);
  
  Serial.println(" cm");

  delay(100);  // Wait for 100 milliseconds before next measurement
}

//  Note:

 // This digital scale has an accuracy of +/- 5cm]





