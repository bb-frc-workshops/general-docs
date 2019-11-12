1. **Migrate code to wpilibj simulator/HAL framework**
    1. Test basic HAL framework with mock classes
        - [github repo for HAL](https://github.com/wpilibsuite/allwpilib)
    1. Create serial schema for ardunio communication
	1. Implement jni hook for HAL serialization
	1. Create new lib for Arduino logic by hardware version
	1. Create PC test harness to test Arduino via USB serial communication
    1. Implement basic components
        - Implement serial response message from Arduino to Raspberry PI for error handling
		- Implement Raspberry PI message to PC for error feedback (already done in wpilibj?)
        - Implement Joystick on Raspberry PI (lready done in wpilibj?)
		- Implement Arduino firmware for PWM, from differentialDrive jni
1. **IDE Support upgrades***
    1. Refactor code to be cleaner and more flexible
	1. Add easy to append documentation area
    1. Allow for running locally
    1. Add "Save" option
    1. Allow for multiple files
	1. Integrate FRC driver station
1. **Add support for actuators**
    1. choose actuators (servos, analog vs digital, etc)
    1. pitch actuators and why to team
    1. purchase actuators
    1. Implement Hardware Abstraction Layer jni
	1. Implement firmware in Arduino hardware library
    1. write sample code, integrate into doc in IDE
    1. train other engineers
1. **Add support for sensors**
    1. choose sensors (switches, cameras, analog vs digital, etc)
    1. pitch sensors and why to team
    1. purchase sensors
    1. write wpilibj override
    1. write sample code, integrate into doc in IDE
    1. train other engineers
1. **Migrate to VSCode**
    1. move web services for build to local machine
        - JVM build locally
        - download hook/plug-in
        - iOS vs windows
    1. create detailed list for installing and setup
1. **Introduction and lab on CAD**
    1. Drafting principles
        - views (Ortho, perspective, iso, etc)
        - choice of program (SolidWorks, ZQs one?)
1. **Electrical basics**
    1. wiring and schematics
    1. Signals types (analog, digital, CAN, & PWM)
    1. pull-ups, pull-downs, and shielding & interference
    1. Tools - Strippers, cutters, crimping
1. **Mechanical basics**
    1. Frames and mounting
    1. Accessibility and construction
    1. Types actuators and motions they create
1. **Machining**

Useful Links:

[HAL](https://first.wpi.edu/FRC/roborio/release/docs/cpp/annotated.html)

[HALUtil](https://first.wpi.edu/FRC/roborio/release/docs/java/edu/wpi/first/wpilibj/hal/HALUtil.html)
