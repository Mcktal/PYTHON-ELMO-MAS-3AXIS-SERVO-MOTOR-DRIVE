# PYTHON-ELMO-MAS-3AXIS-SERVO-MOTOR-DRIVE
Python code for direct controlling over 'Elmo' servo controller kit without any GUI 

# Description
This Python code controlling a motor via a UDP connection, monitoring and recording data from the motor's sensors. the application makes manipulation over data and store those in excel form, It includes a graphical user interface (GUI) created using the tkinter library. in simple words: This code represents a basic motor control and data recording application with a user-friendly GUI. It connects to a motor controller over UDP, sends commands to configure the motor, records sensor data, and saves it to an Excel file. Below is a breakdown of the code:

Define IP and Port: It defines the IP address and port number to establish a connection with a UDP server.

Creating DataFrames: Three empty DataFrames (gdata, position_data, speed_data, and current_data) are created to store data from different sensors. These DataFrames will be used to record and store data over time.

process_input Function: This function is used to process and add user data into the DataFrames. It takes two parameters, a value (a) and a sensor type (b). Depending on the sensor type, it calculates various properties like time differences (dt), velocity (v1), and performs FFT on sensor values.

remove_semicolon Function: This function is used to remove a semicolon from the end of a string.

convert_to_num Function: This function converts a string to a number, either an integer or a float, depending on the content of the string.

convert_pos_to_deg Function: This function converts a position value from revolutions to degrees.

comm Function: This function is responsible for communication with the UDP server. It sends a byte message to the server, receives a response, processes the data, and then adds it to the appropriate DataFrame.

Define Byte Parameters: Several byte messages are defined, such as motor initiation, motor status, speed command initiation, and others, which will be sent to control the motor.

start_motor Function: This function is called when the "START" button in the GUI is pressed. It establishes a connection to the UDP server, sends various commands to configure the motor, and starts it.

stop_motor Function: This function is called when the "STOP" button in the GUI is pressed. It sends a stop command to the motor and stops the application.

data_extraction Function: This function is called when the "START_EXTRACTION" button in the GUI is pressed. It initiates a thread that continuously requests data from the motor and stores it in the DataFrames. This data is then saved to an Excel file.

perform_data_extraction Function: This function is executed in a separate thread. It continually sends requests to the motor, updates the DataFrames, and saves data to an Excel file. It also handles keyboard interrupts to exit the program gracefully.

Creating the GUI: The code creates a simple GUI window using tkinter. It includes "START," "STOP," and "START_EXTRACTION" buttons for controlling the motor and data recording.

Main Loop: The script enters the main loop using root.mainloop(), which keeps the GUI running and responsive.


