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
	if the interface gives the target posiion for the robot arm.
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

	Finished the feasibility study.
	
	
