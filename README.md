# MULTITREAD_CODE_ARDUINO
MULTITREAD_CODE_ARDUINO

DOWNLOAD LIBRARY LINK -  https://github.com/atulkumar6556/-Multithread-_in_Arduino/blob/main/TimedAction-master.zip


##RUN MULTIPLE TASKS AT SAME TIME

    #include <TimedAction.h>
    #include "thread1.h"
    #include "thread2.h"
    #include "flashing.h"
    //https://forum.arduino.cc/u/atul6556/

    void setup() {
      pinMode(13,OUTPUT);
      Serial.begin(115200);
      changeText();
      flash();
    }


    void maintask(){
      Serial.println("Main Task Running .....");
      digitalWrite(13,HIGH);
    }

    //
    void changeText(){  
      Serial.println("https://forum.arduino.cc/u/atul6556/");
    }
    //

    TimedAction mainThread = TimedAction(1000,maintask);
    TimedAction task1Thread = TimedAction(1000,task1);
    TimedAction task2Thread = TimedAction(5000,task2);
    TimedAction flashThread = TimedAction(6000,flash);





    void loop() {
      mainThread.check();
      task1Thread.check();
      task2Thread.check();
      flashThread.check();



    }
    //https://forum.arduino.cc/u/atul6556/
