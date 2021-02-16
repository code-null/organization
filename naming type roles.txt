#----------------------------------------------- Naming conventions ---------------------------------------------------
* 	= Any Character
+ 	= Number
# 	= Letter
% 	= Letter or number
" 	= Nato Alphabet
? 	= word
()	= Optional
{} 	= Interpolation using camel casing

			| Technical	| Reference Name			| Official Name 			| Example
			| 	ID		|							|							|
#----------------------------------------------------------------------------------------------------------------------
 Devices 	| D#### 	| {any}						| (Code) Delta " || D-####	| DZTDI - raspi - Delta Omega				| DHOLW - homeComputer - D-HOLW;
 Servers 	| S%%%% 	| {serverFunction}Server	| (Code) Sierra " || S-%%%	| S1452 - mngCaseiumServer - Sierra Alpha	| S1352 - comSideToMain - Code S-135
 Programs	| P#%%% 	| {officialNameW/O"Code"}	| (Code) ?(?-****) 			| PC133 - caesium - Code Caesium			| PRT02 - roamingTool - Roaming-Tool
 Components	| C++++		| {functionType}			| ?(?-****) 				| C1508 - mainMenuIn - Main Menu			| C4587 - alertModalOut - Alert-Modal


#------------------------------------------------------- Types --------------------------------------------------------
Types hint at the purpose of the device, server or component

				| Short	| Description																| Used for
#----------------------------------------------------------------------------------------------------------------------
 Manage			| mng	| Accessing databases for read/write operations and return data				| Devices, Server
 Communicate	| com	| Handling communication between two or more programs, servers or devices	| Devices, Server
 Input			| in	| Getting user input														| Components
 Output			| out	| Displaying data only														| Components
 Inquire		| inq	| Communicating with a server to get data									| Components
 Engage			| eng	| Communicating with a server to post or modify data						| Components


#--------------------------------------------------- Base User Roles ---------------------------------------------------
			| Description
#----------------------------------------------------------------------------------------------------------------------
Overwatch	| has admin privilege for all programs
Admin		| is allowed to manipulate settings for a given program and manage users
Unit		| can use program, within the limits set by an Admin





