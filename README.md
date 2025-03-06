# LED blinking with switch Using Arduino Uno
This is simple led blinking with switch using Arduino uno 

## Componets Used 
- Arduino Uno
- LED
- Switch
- 125 ohm Resistor
- Breadboard
- jumper Wire
- (You can also online https://www.tinkercad.com/ for Online Simulation )

## Code
```cpp
// Define pin numbers
int ledPin = 12;     // Pin connected to the LED
int switchPin = 6;   // Pin connected to the switch

void setup()
{
    // Set LED pin as OUTPUT so we can turn it ON and OFF
    pinMode(ledPin, OUTPUT);

    // Set switch pin as INPUT with internal pull-up resistor
    // This makes the pin normally HIGH, and it will go LOW when the switch is pressed
    pinMode(switchPin, INPUT_PULLUP);
}

void loop()
{
    // Read the current state of the switch (LOW when pressed, HIGH when not pressed)
    bool switch_data = digitalRead(switchPin);

    // Check if the switch is pressed
    if (switch_data == LOW)    // Switch is pressed (pulled to ground)
    {
        digitalWrite(ledPin, HIGH);  // Turn ON the LED
    }
    else    // Switch is not pressed
    {
        digitalWrite(ledPin, LOW);   // Turn OFF the LED
    }

    // Short delay to debounce the switch slightly (optional, can be adjusted or removed)
    delay(50);
}
