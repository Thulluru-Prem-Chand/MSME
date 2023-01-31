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
    int buttonState = 0;

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
    ![Exp5](https://user-images.githubusercontent.com/74300223/215634346-c5f77b1c-617a-4705-b1a9-74313f3f10ae.png)

