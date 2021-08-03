# Ultrasonic-Distance-Sensor

![image](https://user-images.githubusercontent.com/86917834/127994398-b38c7b1d-367c-408f-a3fe-7e68a1182eea.png)
![image](https://user-images.githubusercontent.com/86917834/127994427-22d91308-8e7a-445e-8c01-4dc3c419d511.png)

#define echo 5
#define trig 6
#define led 13
void setup()
{
pinMode(trig, OUTPUT);
pinMode(echo,INPUT);
pinMode(led,OUTPUT);
Serial.begin(9600);
}
void loop()
{
long time,dist;
digitalWrite(trig,LOW);
delayMicroseconds(2);
digitalWrite(trig,HIGH);
delayMicroseconds(10);
digitalWrite(trig,LOW);
time = pulseIn(echo,HIGH);
dist = time/3/29.1;       //3 seconds as it is requisted
Serial.println(dist);
delay(1000);
  if (dist<100)
{digitalWrite(led,HIGH);}
else
{digitalWrite(led,LOW);}
  }
