# Rasberry-pi
Activities from infosys springboard

# Varying the brightness of LED

import RPi.GPIO as GPIO
led_pin = 18
GPIO.setmode(GPIO.BCM)
GPIO.setup(led_pin, GPIO.OUT)
pwm_led = GPIO.PWM(led_pin, 500)
pwm_led.start(100)
while True:
   duty_s = input("Enter Brightness (0 to 100):")
   duty = int(duty_s)
   pwm_led.ChangeDutyCycle(duty)

# Connecting a push button
import RPi.GPIO as GPIO # Import Raspberry Pi GPIO library
import time
GPIO.setmode(GPIO.BOARD)# Use physical pin numbering
GPIO.setup(10, GPIO.IN, pull_up_down=GPIO.PUD_DOWN)# Set pin 10 to be an input pin and set initial value to be pulled down(off)
while True:
    btn_input = GPIO.input(10)
    if btn_input == GPIO.HIGH:
        print('Button is Pressed')
        time.sleep(0.3)




