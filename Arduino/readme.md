# Arduino Training

### 1. Interfacing of Arduino with LED
- **Code :**
```
    void setup()
    {
      pinMode(13, OUTPUT);
    }

    void loop()
    {
      digitalWrite(13, HIGH);
      delay(1000); 
      digitalWrite(13, LOW);
      delay(1000); 
    }
```
- **Circuit :**
    ![Exp1](https://user-images.githubusercontent.com/74300223/215528814-c579d9fa-c98a-4da7-a615-42f9fb95a057.png)

### 2. Interfacing of Arduino with 3 LED's
- **Code :**
```
    void setup()
    {
      pinMode(13, OUTPUT);
      pinMode(12, OUTPUT);
      pinMode(11, OUTPUT);
    }

    void loop()
    {
      digitalWrite(13, HIGH);
      delay(1000); 
      digitalWrite(13, LOW);
      delay(1000); 

      digitalWrite(12, HIGH);
      delay(1000); 
      digitalWrite(12, LOW);
      delay(1000); 

      digitalWrite(11, HIGH);
      delay(1000); 
      digitalWrite(11, LOW);
      delay(1000); 
    }
```
- **Circuit :**
    ![Exp2](https://user-images.githubusercontent.com/74300223/215529192-38beae58-626e-4e93-8f08-41e2e09e66f5.png)
    
### 3. Interfacing of arduino with Led to get on with push button
- **Code :**
```   
    void setup()
    {
      pinMode(2, INPUT);
      pinMode(13, OUTPUT);
      Serial.begin(9600);
    }
    
    void loop()
    {
      int buttonState = digitalRead(2);
      if (buttonState == HIGH){
        digitalWrite(13, HIGH);
      } else {
        digitalWrite(13, LOW);
      }
    }
```
- **Circuit :**
    ![Exp3](https://user-images.githubusercontent.com/74300223/215542725-599c43c2-de57-43ff-87e2-f9320209762d.png)

### 4. Interfacing of Arduino with Buzzer
- **Code :**
```
    void setup()
    {
      pinMode(9, OUTPUT);
    }

    void loop()
    {
      tone(9, 1000); // Here 1000 refers to 1KHz
      delay(1000); 
      noTone(9);
      delay(1000); 
    }
```
- **Circuit :**
    ![Exp4](https://user-images.githubusercontent.com/74300223/215545828-5a91040f-8fa6-419c-9df9-7b13729a3006.png)

### 5. Interfacing of Arduino wuth 3 LED's and 3 Push Buttons
- **Code :**
```
    void setup()
    {
      pinMode(2, INPUT);
      pinMode(3, INPUT);
      pinMode(4, INPUT);
      pinMode(13, OUTPUT);
      pinMode(11, OUTPUT);
      pinMode(9, OUTPUT);
      Serial.begin(9600);
    }

    void loop()
    {
      int red = digitalRead(2);
      int yellow = digitalRead(3);
      int green = digitalRead(4);

      if (red == HIGH){
        digitalWrite(13, HIGH);
      } else {
        digitalWrite(13, LOW);
      }

      if (yellow == 1){
        digitalWrite(11, HIGH);
      } else {
        digitalWrite(11, LOW);
      }

      if (green == 1){
        digitalWrite(9, HIGH);
      } else {
        digitalWrite(9, LOW);
      }
    }
```

- **Circuit :**
    ![Exp5](https://user-images.githubusercontent.com/74300223/215637182-418a02eb-f50c-4e35-926a-21da2a0a788e.png)

### 6. Interfacing of Arduino with Buzzer and Push button
- **Code :**
```
    void setup()
    {
      pinMode(2, INPUT);
      pinMode(13, OUTPUT);
      Serial.begin(9600);
    }

    void loop()
    {
      int buzz = digitalRead(2);

      if (buzz == HIGH){
        tone(13, 1000);
      } else {
        noTone(13);
      }
    }
```
- **Circuit :**
    ![Exp6](https://user-images.githubusercontent.com/74300223/215641071-6494c00c-8c8a-4d72-8e0a-48dbd6a8ecd7.png)

### 7. Interfacing of Arduino with Gas sensor and Buzzer
- **Code :**
```
    void setup(){
      pinMode(2,OUTPUT);
      pinMode(A0,INPUT);
      Serial.begin(9600);
    }

    void loop(){
      int gas = analogRead(A0);
      if(gas > 90){
        Serial.print(gas);
        Serial.println(" Gas Smoke Detected");
        tone(2,1000);
        delay(1000);
      }
      else{
        Serial.print(gas);
        Serial.println(" No Gas Smoke Detected");
        noTone(2);
        delay(1000);
      }
    }
```
- **Circuit :**
    ![Exp7](https://user-images.githubusercontent.com/74300223/215739623-4bf0df55-7b2f-493c-8e6a-c95aba9aaea0.png)
    
### 8. Interfacing of Arduino with UlstraSonic Sensor HC-SR04
- **Code :**
```
    int trig = 3;
    int echo = 2;

    void setup(){
      pinMode(trig, OUTPUT);
      pinMode(echo, INPUT);
      Serial.begin(9600);
    }

    void loop(){
      int distOfObj, timeOfPulse;

      digitalWrite(trig,LOW);
      delay(2);
      digitalWrite(trig,HIGH);
      delay(10);
      digitalWrite(trig,LOW);

      timeOfPulse = pulseIn(echo, HIGH);
      distOfObj = (timeOfPulse/2)*0.0344;

      if(distOfObj >=335 || distOfObj <=2){
        Serial.println("No Object With in Range");
      }
      else{
        Serial.print("Object Detected at ");
        Serial.print(distOfObj);
        Serial.println(" cm");
      }
      delay(100);
    }
```
- **Circuit :**
    ![Exp8](https://user-images.githubusercontent.com/74300223/215751408-dfa4f679-d371-4cda-8168-5246290e8e2d.png)
    
### 9. Interfacing of Arduino with Common Cathode Seven Segment Display
- **Code :**
```
    //printing 1098 on  segment display
    int a=1,b=3,c=5,d=7,e=9,f=13,g=11;
    void setup(){
      pinMode(a, OUTPUT);
      pinMode(b, OUTPUT);
      pinMode(c, OUTPUT);
      pinMode(d, OUTPUT);
      pinMode(e, OUTPUT);
      pinMode(f, OUTPUT);
      pinMode(g, OUTPUT);

    }

    void loop(){
      //printing 1
      digitalWrite(a, LOW);
      digitalWrite(b, HIGH);
      digitalWrite(c, HIGH);
      digitalWrite(d, LOW);
      digitalWrite(e, LOW);
      digitalWrite(f, LOW);
      digitalWrite(g, LOW);
      delay(1000);

      //printing 0
      digitalWrite(a, HIGH);
      digitalWrite(b, HIGH);
      digitalWrite(c, HIGH);
      digitalWrite(d, HIGH);
      digitalWrite(e, HIGH);
      digitalWrite(f, HIGH);
      digitalWrite(g, LOW);
      delay(1000);

      //printing 9
      digitalWrite(a, HIGH);
      digitalWrite(b, HIGH);
      digitalWrite(c, HIGH);
      digitalWrite(d, LOW);
      digitalWrite(e, LOW);
      digitalWrite(f, HIGH);
      digitalWrite(g, HIGH);
      delay(1000);

      //printing 8
      digitalWrite(a, HIGH);
      digitalWrite(b, HIGH);
      digitalWrite(c, HIGH);
      digitalWrite(d, HIGH);
      digitalWrite(e, HIGH);
      digitalWrite(f, HIGH);
      digitalWrite(g, HIGH);
      delay(1000);
    }
```
- **Circuit :**
    ![Exp91](https://user-images.githubusercontent.com/74300223/215814770-1904f66e-3957-4008-ab1e-5ed244fbc849.png)
    
### 10. Interfacing of Arduino with Ultrasonic sensor and LED
- **Code :**
```
    int trig = 3;
    int echo = 2;

    void setup(){
      pinMode(trig, OUTPUT);
      pinMode(echo, INPUT);
      pinMode(13, OUTPUT);
      Serial.begin(9600);
    }

    void loop(){
      int distOfObj, timeOfPulse;

      digitalWrite(trig,LOW);
      delay(2);
      digitalWrite(trig,HIGH);
      delay(10);
      digitalWrite(trig,LOW);

      timeOfPulse = pulseIn(echo, HIGH);
      distOfObj = (timeOfPulse/2)*0.0344;

      if(distOfObj >=332 || distOfObj <=2){
        Serial.println("No Object With in Range");
        digitalWrite(13, LOW);
      }
      else{
        Serial.print("Object Detected at ");
        Serial.print(distOfObj);
        Serial.println(" cm");
        digitalWrite(13, HIGH);
      }
      delay(500);
    }
```
- **Circuit :**
    ![Exp10](https://user-images.githubusercontent.com/74300223/216012833-fe836368-f48d-4f77-9240-0e6497c46696.png)

### 11. Interfacing of Arduino with Gas Sensor, Buzzer, Green and Red LED's indication
- **Code :**
```
    void setup(){
      pinMode(2,OUTPUT);
      pinMode(A0,INPUT);
      pinMode(13,OUTPUT);
      pinMode(9,OUTPUT);
      Serial.begin(9600);
    }

    void loop(){
      int gas = analogRead(A0);
      if(gas > 125){
        Serial.print(gas);
        Serial.println(" Gas Smoke Detected");
        tone(2,1000);
        digitalWrite(13,HIGH);
        digitalWrite(9,LOW);
        delay(100);
      }
      else{
        Serial.print(gas);
        Serial.println(" No Gas Smoke Detected");
        noTone(2);
        digitalWrite(13,LOW);
        digitalWrite(9,HIGH);
        delay(100);
      }
    }
```
- **Circuit :**
    ![Exp11](https://user-images.githubusercontent.com/74300223/216018111-922e4183-4153-405c-82c9-9e30d3c2a4d3.png)

### 12. Interfacing of Arduino with Temperature Sensor TMP36
- **Code :**
```
    void setup()
    {
      pinMode(A0, INPUT);
      Serial.begin(9600);
    }

    void loop()
    {
      float volt = analogRead(A0) * (5000 / 1024);
      float temp = (volt-500)/10;
      Serial.print("Room Temperature : ");
      Serial.print(temp);
      Serial.println(" Celcius");
      delay(500);
    }
```
- **Circuit :**
    ![Exp12](https://user-images.githubusercontent.com/74300223/216025622-95c0e11d-db1e-4901-a324-e31a519bbb38.png)

### 13. Interfacing of Arduino with Water Sensor SCN18
- **Code :**
``` 
    void setup() {
        pinMode(A2, INPUT);
        Serial.begin(9600);
    }

    void loop() {
        int level = analogRead(A2);
        if (level == 0) {
            Serial.println("Water Level: Empty");
        }
        else if (level > 0 && level <= 420) {
            Serial.println("Water Level: Low");
        }
        else if (level > 420 && level <= 520) {
            Serial.println("Water Level: Medium");
        }
        else if (level > 520) {
            Serial.println("Water Level: High");
        }
    }
```
- **Circuit :**
    ![Exp13](https://user-images.githubusercontent.com/74300223/216037402-36f4d0cc-e991-47a7-be38-6b784996a115.png)

### --  Interfacing of Arduino with Rain Sensor SCN18, with Indication of 4 LED's
- **Code:**
```
    void setup() {

        pinMode(A2, INPUT);
        pinMode(2,OUTPUT);
        pinMode(4,OUTPUT);
        pinMode(6,OUTPUT);
        pinMode(8,OUTPUT);
        
        Serial.begin(9600);
    }

    void loop() {
        int level = analogRead(A2);
        Serial.print(level);
       
        if (level == 0) {
            Serial.println(" Water Level: Empty");
            digitalWrite(2,1);
            digitalWrite(4,0);
            digitalWrite(6,0);
            digitalWrite(8,0);
            
        }
        else if (level > 0 && level <= 420) {
            Serial.println(" Water Level: Low");
            digitalWrite(2,0);
            digitalWrite(4,1);
            digitalWrite(6,0);
            digitalWrite(8,0);
            
        }
        else if (level > 420 && level <= 650) {
            Serial.println(" Water Level: Medium");
            digitalWrite(2,0);
            digitalWrite(4,0);
            digitalWrite(6,1);
            digitalWrite(8,0);
        }
        else if (level > 650) {
          digitalWrite(2,0);
          digitalWrite(4,0);
          digitalWrite(6,0);
          digitalWrite(8,1);
            Serial.println(" Water Level: High");
        }
    }
```

### 14. Interfacing of Arduino with Gas MQ125 And temp Sensor TMP35
- **Code :**
```
    void setup(){
      pinMode(2,OUTPUT);
      pinMode(A2,INPUT);

      pinMode(A0,INPUT);
      pinMode(13,OUTPUT);
      Serial.begin(9600);
    }

    void loop(){
      int gas = analogRead(A2);

      float volt = analogRead(A0) * (5000 / 1024);
      float temp = (volt-500)/10;

      if(gas > 125){
        Serial.print(gas);
        Serial.println(" Gas Smoke Detected");
        tone(2,1000);
      }
      else{
        Serial.print(gas);
        Serial.println(" No Gas Smoke Detected");
        noTone(2);
      }

      if(temp>30){
        Serial.print("Room Temperature : ");
        Serial.print(temp);
        Serial.println(" Celcius");
        digitalWrite(13,HIGH);
      }
      else{
        Serial.print("Room Temperature : ");
        Serial.print(temp);
        Serial.println(" Celcius");
        digitalWrite(13,LOW);
      }
      delay(1000);

    }
```
- **Circuit :**
    ![Exp14](https://user-images.githubusercontent.com/74300223/216251130-ba1a7c03-b581-4b59-8a1f-2b2cda19a10d.png)
    
    
### 15. Interfacing of Arduino with Soil Moisture sensor and LED's
- **Code :**
```   
    int moisture = 0;
    void setup(){
        pinMode(A0, INPUT);
        pinMode(7, OUTPUT);
        pinMode(9, OUTPUT);
        pinMode(12, OUTPUT);
        Serial.begin(9600);
    }

    void loop(){
        moisture = analogRead(A0);
        Serial.print("Moisture Content : ");
        Serial.print(moisture);

        if (moisture < 300) {
            digitalWrite(7, 0);
            digitalWrite(9, 0);
            digitalWrite(12, 1);
            Serial.println(" LOW Level");
        } 
        else if (moisture >=300 && moisture < 700) {
            digitalWrite(7, 0);
            digitalWrite(9, 1);
            digitalWrite(12, 0);
            Serial.println(" MEDIUM Level");
        } 
        else{
            digitalWrite(7, 1);
            digitalWrite(9, 0);
            digitalWrite(12, 0);
            Serial.println(" HIGH Level");
        }
        delay(500);
    }
```

- **Circuit :**
    ![Exp15](https://user-images.githubusercontent.com/74300223/216291219-1c8622cf-41e6-4bd1-8f88-fcd6c54612e8.png)
    
### 16. Interfacing of Arduino with IR Sensor HW-201
- **Code :**
```
    void setup() {
      pinMode(2,INPUT);
      pinMode(12,OUTPUT);
      pinMode(10,OUTPUT);
      Serial.begin(9600);
    }

    void loop() {
      if (digitalRead(2)==0){
          digitalWrite(12,HIGH);
          digitalWrite(10,LOW);
          Serial.println("Object Detected");
        }
      else{
          digitalWrite(10,HIGH);
          digitalWrite(12,LOW);
          Serial.println("No Object Detected");
        }

    }
```
- **Circuit :**
    
