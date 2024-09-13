#define NUM_LEDS 8  // Define the number of LEDs

// Create an array of LED pins
int leds[NUM_LEDS] = {D0, D1, D2, D3, D4, D5, D6, D7};

void setup() {
  // Set all the LED pins as OUTPUT using a loop
  for (int i = 0; i < NUM_LEDS; i++) {
    pinMode(leds[i], OUTPUT);
  }
}

void loop() {
  for (int i = 0; i < 3; i++) {
    chaseEffect();        // Combination 1, run 3 times
  }
  
  for (int i = 0; i < 5; i++) {
    blinkingPair();       // Combination 2, run 5 times
  }
  
  for (int i = 0; i < 8; i++) {
    centerToEdge();       // Combination 3, run 8 times
  }
  
  for (int i = 0; i < 8; i++) {
    alternatingGroups();  // Combination 4, run 8 times
  }
}

// Combination 1: Chase Effect (Back and Forth)
void chaseEffect() {
  // Light up LEDs from D0 to D7
  for (int i = 0; i < NUM_LEDS; i++) {
    digitalWrite(leds[i], HIGH);
    delay(50);
    digitalWrite(leds[i], LOW);
  }

  // Light up LEDs in reverse from D7 to D0
  for (int i = NUM_LEDS - 1; i >= 0; i--) {
    digitalWrite(leds[i], HIGH);
    delay(50);
    digitalWrite(leds[i], LOW);
  }
}

// Combination 2: Blinking Pair (Odd and Even Together)
void blinkingPair() {
  // Odd LEDs ON, Even LEDs OFF
  for (int i = 0; i < NUM_LEDS; i++) {
    if (i % 2 == 0) {
      digitalWrite(leds[i], HIGH);  // Odd LEDs ON
    } else {
      digitalWrite(leds[i], LOW);   // Even LEDs OFF
    }
  }
  delay(200);

  // Even LEDs ON, Odd LEDs OFF
  for (int i = 0; i < NUM_LEDS; i++) {
    if (i % 2 == 0) {
      digitalWrite(leds[i], LOW);   // Odd LEDs OFF
    } else {
      digitalWrite(leds[i], HIGH);  // Even LEDs ON
    }
  }
  delay(200);
  for (int i = 0; i < NUM_LEDS; i++) { //all LEDs off
    digitalWrite(leds[i], LOW);
  }
}

// Combination 3: Center to Edge (Expanding Outwards)
void centerToEdge() {
  int center1 = NUM_LEDS / 2 - 1;  // Middle two LEDs (LED4 and LED5)
  int center2 = NUM_LEDS / 2;

  digitalWrite(leds[center1], HIGH);
  digitalWrite(leds[center2], HIGH);
  delay(100);

  for (int i = 1; i <= center1; i++) {
    digitalWrite(leds[center1 - i], HIGH);  // Expanding left
    digitalWrite(leds[center2 + i], HIGH);  // Expanding right
    delay(100);
  }

  // Turn off all LEDs
  for (int i = 0; i < NUM_LEDS; i++) {
    digitalWrite(leds[i], LOW);
  }
  delay(100);
}

// Combination 4: Alternating Groups (Two Groups of Four)
void alternatingGroups() {
  // Group A (LED1 to LED4)
  for (int i = 0; i < NUM_LEDS / 2; i++) {
    digitalWrite(leds[i], HIGH);
  }
  delay(100);

  // Group A OFF, Group B ON (LED5 to LED8)
  for (int i = 0; i < NUM_LEDS / 2; i++) {
    digitalWrite(leds[i], LOW);
  }
  for (int i = NUM_LEDS / 2; i < NUM_LEDS; i++) {
    digitalWrite(leds[i], HIGH);
  }
  delay(100);

  // Group B OFF
  for (int i = NUM_LEDS / 2; i < NUM_LEDS; i++) {
    digitalWrite(leds[i], LOW);
  }
}
