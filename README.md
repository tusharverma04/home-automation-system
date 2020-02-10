# home-automation-system
//The main objective of this project is to develop a home automation system using an Arduino board with wifi module being remotely controlled by an Android OS smart phone. As technology is advancing so houses are also getting smarter. Modern houses are gradually shifting from conventional switches to centralized control system, involving remote controlled switches. This paper presents a low cost flexible and reliable home automation system with additional security using Arduino microcontroller, with IP connectivity through local Wi- Fi for accessing and controlling devices by authorized user remotely using Smart phone application. The proposed system is server independent and uses Internet of things to control human desired appliances starting from industrial machine to consumer goods. The user can also use different devices for controlling by the help of web-browser, smart phone or IR remote module.  //

#include <SoftwareSerial.h>
SoftwareSerial DebugSerial(2, 3); // RX, TX

#include <BlynkSimpleStream.h>

// You should get Auth Token in the Blynk App.
// Go to the Project Settings (nut icon).
char auth[] = "5CsD_uyTf8mlIf8oqOnxBz5WuEZZUI9n"; //comes in email everytime you register with blynk app. 


void setup()
{
  // Debug console
  DebugSerial.begin(9600);

  // Blynk will work through Serial
  // Do not read or write this serial manually in your sketch
  Serial.begin(9600);
  Blynk.begin(Serial, auth);
}

void loop()
{
  Blynk.run();
}
