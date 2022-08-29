# ESP32-Pinoo
An Arduino library to use ESP32 cards over Wifi on ESP32 boards.


Quick start
-----------

```
#include <Arduino.h>
#include <BLEMidi.h>

void setup() {
  Serial.begin(115200);
  Serial.println("Initializing bluetooth");
  BLEMidiServer.begin("Basic MIDI device");
  Serial.println("Waiting for connections...");
  //BLEMidiServer.enableDebugging();  // Uncomment if you want to see some debugging output from the library
}

void loop() {
  if(BLEMidiServer.isConnected()) {             // If we've got a connection, we send an A4 during one second, at full velocity (127)
      BLEMidiServer.noteOn(0, 69, 127);
      delay(1000);
      BLEMidiServer.noteOff(0, 69, 127);        // Then we stop the note and make a delay of one second before returning to the beginning of the loop
      delay(1000);
  }
}
```

Check the header file [here](https://github.com/max22-/ESP32-BLE-MIDI/blob/master/src/utility/Midi.h) to view all available MIDI commands and callbacks.
Future work
-----------

- Add some more examples
- Add documentation, with Doxygen ?
- Add keywords.txt for Arduino IDE

- Add support for realtime messages ?
- Add debugging messages in BLEMidiServer ?
- Better debug function

Message to users
----------------
I would be glad to see your projects! Don't hesitate to drop me an e-mail. (dnzayan@hotmail.com)
