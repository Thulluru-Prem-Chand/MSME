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

### 4. Interfacing of Arduino with Buzzer
