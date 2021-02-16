# Naming conventions

The naming convention should help with consitent naming and with identifying what each thing is.

## Symbols

\* = Any Character <br>
\+ = Number <br>
\# = Letter <br>
\% = Letter or number <br>
\" = Nato Alphabet <br>
\? = word <br>
\() = Optional <br>
\{} = Interpolation using camel casing <br>

## Naming Table

|            | Technical ID | Reference Name          | Official Name                | Example 1                               | Example 2                           |
| ---------- | ------------ | ----------------------- | ---------------------------- | --------------------------------------- | ----------------------------------- |
| Devices    | D\#\#\#\#    | {any}                   | (Code) Delta " or D-\#\#\#\# | DZTDI - raspi - Delta Omega             | DHOLW - homeComputer - D-HOLW       |
| Servers    | S\%\%\%\%    | {serverFunction}Server  | (Code) Sierra " or S-\%\%\%  | S1452 - mngCaseiumServer - Sierra Alpha | S1352 - comSideToMain - Code S-135  |
| Programs   | P\#\%\%\%    | {officialNameW/O"Code"} | (Code) ?(?-\*\*\*\*)         | PC133 - caesium - Code Caesium          | PRT02 - roamingTool - Roaming-Tool  |
| Components | C\+\+\+\+    | {functionType}          | ?(?-\*\*\*\*)                | C1508 - mainMenuIn - Main Menu          | C4587 - alertModalOut - Alert-Modal |

# Types

Types hint at the purpose of the device, server or component and helps ensuring it is only doing one thing. This way there should't be any side effects.

|             | Short | Description                                                             | Used for        |
| ----------- | ----- | ----------------------------------------------------------------------- | --------------- |
| Manage      | mng   | Accessing databases for read/write operations and return data           | Devices, Server |
| Communicate | com   | Handling communication between two or more programs, servers or devices | Devices, Server |
| Input       | in    | Getting user input                                                      | Components      |
| Output      | out   | Displaying data only                                                    | Components      |
| Inquire     | inq   | Communicating with a server to get data                                 | Components      |
| Engage      | eng   | Communicating with a server to post or modify data                      | Components      |

# Base User Roles

The Base User Roles are a general way categorizing different levels of access. For each individual program, different names and sub levels can be used, but they all need to have a base role assigned, for the global eco system. They can also be thought of as global role identifiers or a broad category. Imagine a Cessna and Airbus A380, which can do different things, but are both categorized as fixed-wing aircraft.

|           | Description                                                            | Intended for                                          |
| --------- | ---------------------------------------------------------------------- | ----------------------------------------------------- |
| Overwatch | Has admin privilege for all programs in the given sub-ecosystem        | IT-Department, Person in charge of deploying software |
| Admin     | Is allowed to manipulate settings for a given program and manage users | Team-Leaders, Project-Managers                        |
| Unit      | Can use program, within the limits set by an Admin                     | Endusers, Employees                                   |
