work-protocol
--------------------------------------------------------------------------------

13:00-15:00 HOME 18/10/2015 -- 2h

	-Familiarisation with the used platform and reading the documentation

13:57-17:57 HOME 20/10/2015 -- 4h

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
			
[firmata firmware](https://github.com/firmata/arduino)

[list of firmata libraries for pc](http://www.firmata.org/wiki/Download)

[example of adding functionality to the firmata firmware](http://www.instructables.com/id/Going-Beyond-StandardFirmata-Adding-New-Device-Sup/step5/Adding-STEPPERDATA-Subcommands-to-Both-the-Client-/)

13:00-16:00 B434 27/10/2015 -- 3h
			
	Diskussed the parts and the generall architecure of the project. 
	Started to work on the feasability study and divided the workload.
	PC side code is done by me. Arduino side code is done by Liu.
	
	
