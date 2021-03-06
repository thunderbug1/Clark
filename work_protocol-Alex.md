work-protocol
--------------------------------------------------------------------------------

18/10/2015 13:00-15:00 HOME -- 2h

	-Familiarisation with the used platform and reading the documentation

20/10/2015 13:57-17:57 HOME -- 4h

	-Setting up the github project.

	-Evaluating different serial protocols for the pc-adruino communication:

		considered option: JsonRPC 

			[JsonRPCServer](https://github.com/cloud-rocket/arduino-json-rpc/blob/master/JsonRPCServer.h)
			Allows remote call of procedures on the arduino by sending the command as a JSON string.
			
			conclusion: JSON adds too much unnecessary overhead to the communication.
	

		possible option: firmata firmware 

			
			It is a standardised general purpose firmware used to access low level functions of the arduino from the pc. 
			It can be extended by custom commands what might be used to add robot specific functions.
			Advantage: It comes with a ready made command parser and protocol structure.
			
			TO DO: evaluate C++ support of the firmata protocol on the Host pc.
				   evaluate complexity of custom function registration
				   
			EDIT: Writing a custom interpreter is probably the simplest and fastest solution.
			
[firmata firmware](https://github.com/firmata/arduino)

[list of firmata libraries for pc](http://www.firmata.org/wiki/Download)

[example of adding functionality to the firmata firmware](http://www.instructables.com/id/Going-Beyond-StandardFirmata-Adding-New-Device-Sup/step5/Adding-STEPPERDATA-Subcommands-to-Both-the-Client-/)

27/10/2015 13:00-16:00 B434  -- 3h
			
	Discussed the parts and the generall architecure of the project. 
	Started to work on the feasability study and divided the workload.
	PC side code is done by me. Arduino side code is done by Liu.

28/10/2015 13:00-17:00 B434 -- 4h	

	Reading about the Leap motion sensor and discussing about how the interface
	could work. Research of how to implement the inverse kinematics which is neccessary
	if the interface gives the target position for the robot arm.
	Considered different options:
	
[OpenRave library](http://openrave.org/docs/latest_stable/)
	
[robotics library](http://www.roboticslibrary.org/api)
	
[concept for custom solution](http://freespace.virgin.net/hugo.elias/models/m_ik2.htm)
	
[orcos](http://www.orocos.org/)
	
	conclusion: orcos seems the most promising and simplest to use
	
30/10/2015 15:00-16:30 HOME -- 1,5h

	Further reading about orcos and evaluation if the use of it is feasible.
	Conclusion: The examples do not seem that complicated. It might be possible.
	Possible problems: it uses Boost (compiling projects with it is always complicated)
	
	TO DO: check if it could be integrated into chris´ software.
			   

01/11/2015 11:00-13:30 HOME -- 2,5h

	Further work on the feasibility study.
	
02/11/2015 18:00-19:30 HOME -- 1,5h

	Finished the feasibility study.

03/11/2015 14:30-18:30 B434 -- 4h

	Made a list of required parts for the battery circuit.
	
	Tested the Leap motion sensor. -> conclusion: it is too inaccurate to use it for the arm-control.
	We will use the Falcon 3d mouse to do that.
	
	Found out that the Romeo controller can not handle the motor contorl and the robot arm control at the
	same time as the controller only has 6 pwm channels and we would need 6+2 channels.
	The new concept is to use a dedicated servo controller board in addition to the romeo controller.
	
06/11/2015 12:20-18:00 B434 -- 5,5h

	Compiling the KDL-library and its´ dependencies.
	
09/11/2015 11:30-12:30 HOME -- 1h

	Set up the project configuration in Visual Studio and successfully built an example project.
	
11/11/2015 15:00-19:00 B434 -- 4h

	Studying the documentation of the KDL-library and working on the DH-parameters.
	Reading datasheets and thinking with Amy about how the Encoders can be connected to the controller.
	
20/11/2015 13:00-14:00 B434 -- 1h

	Further work on the inverse kinematics solver.
	
25/11/2015 11:40-15:40 B434 -- 4h

	The inverse kinematics solver is working now and also tested for some simple cases.
	Reading the documentation of the Maestro servo controller.
	
27/11/2015 14:00-20:00 B434 -- 6h

	First tests with the falcon input device and incorporating the necessary libraries to use it.
	Helping Amy with the code for the encoders.
	
2/12/2015 12:00-14:00 B434 -- 2h
	
	Implementation of spring effect to center the falcon mouse in the middle of its´ coordinate system.
	Implementation of haptic feedback when the IK-solver cannot find a solution anymore.
	
5/12/2015 11:30-15:00 HOME -- 3.5h
	
	Reading Chirs´ code and planing of how to integrate the new code.
	Writing a list of necessary robot functions according to the existing code and serial protocol.
	Problem: the number of sonar sensor is hardcoded to 16. The new robot has less sensors and a 
	change of the number would require rewriting the haptic interface code.
	Planed solution: the new robot should, to be compatible, return standard values for all non existing 
	sensors so that the old code can be used.

9/12/2015 10:00-14:00 HOME -- 4h

	Integrating the Usc references which are necessary for the Maestro servo controller into the server side code.
	Preparing the code to be merged into the existing project by encapsulating the functionality int a single class.
	Implementing the wrist spin functionality in the interface.
	
11/12/2015 14:00-20:00 HOME and B434 -- 6h

	Resolved a problem with crashes when the falcon is initialised in a method instead of the main program.
	Added code to open/close the gripper and to rotate the wrist.
	Tests with different solvers for the inverse kinematics.
	
16/12/2015 13:00-16:00 B434 -- 3h

	Removing bugs and experimenting with different solvers.
	
21/12/2015 11:00-17:00 HOME and B434 -- 6h

	Integrated the code into chris´ software. The software should work now but I cannot test it without the actual hardware.
	The integration into the interface is very simple and one can choose whether to use the falcon for the control of the robot or 	for the arm.
	Added some comments to the code to make it easier to understand.
	
