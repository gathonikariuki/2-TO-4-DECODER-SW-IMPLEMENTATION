# 2-TO-4-DECODER-SW-IMPLEMENTATION
This takes a 2-bit binary input and activates one of four output lines based on the input combination. The system replicates the behaviour of a digital logic decoder using conditional statements, demonstrating understanding of combinational logic and binary mapping.


CODE:
// C++ code
//
void setup()
{
  pinMode(2,INPUT);
  pinMode(3,INPUT);
  pinMode(4, OUTPUT);
  pinMode(5,OUTPUT);
  pinMode(6,OUTPUT);
  pinMode(7,OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  int I0=digitalRead(2);
  int I1=digitalRead(3);
  
  Serial.print("I0=");
  Serial.println(I0);
  Serial.print("I1=");
  Serial.println(I1);
  
  int F3=I0&I1;
  int F2=I0&!I1;
  int F1=!I0&I1;
  int F0=!I0&!I1;
  
  digitalWrite(7,F3 );
  Serial.print("F3=");
  Serial.println(F3);
  digitalWrite(6,F2);
  Serial.print("F2=");
  Serial.println(F2);
  digitalWrite(5,F1);
  Serial.print("F1=");
  Serial.println(F1);
  digitalWrite(4,F0);
  Serial.print("F0");
  Serial.println(F0);
  
  Serial.println();
  delay(500); // Wait for 500 millisecond(s)
}
