Q Introduction to Arduino uno and Breadboard blinking the LED’s.

// C++ code
//
void setup()
{
  pinMode(13, OUTPUT);
}

void loop()
{
  digitalWrite(13, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(13, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
}

<p align="center"><a href="https://githu.com"><img src="https://graph.org/file/665fde4492fa3b20a48d0-4a03dca46fa5577aac.jpg" width="400"></a></p>
