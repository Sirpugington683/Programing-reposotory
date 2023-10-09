myVariable = 0
move = 0

def when_started1():
    global myVariable, move
    while True:
        if controller_1.buttonUp.pressing():
            upperLeft.spin(FORWARD, 70.0, VOLT)
            upperRight.spin(FORWARD, 70.0, VOLT)
            bottomRight.spin(FORWARD, 70.0, VOLT)
            bottomLeft.spin(FORWARD, 70.0, VOLT)
        else:
            while not not controller_1.buttonUp.pressing():
                wait(5, MSEC)
            if not controller_1.buttonUp.pressing():
                upperRight.stop()
                upperLeft.stop()
                bottomRight.stop()
                bottomLeft.stop()
        if controller_1.buttonDown.pressing():
            upperLeft.spin(REVERSE, 70.0, VOLT)
            upperRight.spin(REVERSE, 70.0, VOLT)
            bottomRight.spin(REVERSE, 70.0, VOLT)
            bottomLeft.spin(REVERSE, 70.0, VOLT)
        else:
            while not not controller_1.buttonDown.pressing():
                wait(5, MSEC)
            if not controller_1.buttonDown.pressing():
                upperRight.stop()
                upperLeft.stop()
                bottomRight.stop()
                bottomLeft.stop()
        if controller_1.buttonLeft.pressing():
            upperLeft.spin(REVERSE, 70.0, VOLT)
            upperRight.spin(FORWARD, 70.0, VOLT)
            bottomRight.spin(REVERSE, 70.0, VOLT)
            bottomLeft.spin(FORWARD, 70.0, VOLT)
        else:
            while not not controller_1.buttonLeft.pressing():
                wait(5, MSEC)
            if not controller_1.buttonLeft.pressing():
                upperRight.stop()
                upperLeft.stop()
                bottomRight.stop()
                bottomLeft.stop()
        if controller_1.buttonRight.pressing():
            upperLeft.spin(FORWARD, 70.0, VOLT)
            upperRight.spin(REVERSE, 70.0, VOLT)
            bottomRight.spin(FORWARD, 70.0, VOLT)
            bottomLeft.spin(REVERSE, 70.0, VOLT)
        else:
            while not not controller_1.buttonRight.pressing():
                wait(5, MSEC)
            if not controller_1.buttonRight.pressing():
                upperRight.stop()
                upperLeft.stop()
                bottomRight.stop()
                bottomLeft.stop()
        wait(5, MSEC)

def when_started2():
    global myVariable, move
    while True:
        if controller_1.buttonY.pressing():
            elevaterLift.spin(FORWARD, 70.0, VOLT)
            while not (not controller_1.buttonY.pressing() and controller_1.buttonA.pressing()):
                wait(5, MSEC)
            elevaterLift.stop()
        if controller_1.buttonA.pressing():
            elevaterLift.spin(REVERSE, 70.0, VOLT)
            while not (not controller_1.buttonA.pressing() and controller_1.buttonY.pressing()):
                wait(5, MSEC)
            elevaterLift.stop()
        wait(5, MSEC)

ws2 = Thread( when_started2 )
when_started1()

