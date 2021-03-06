# Guidelines v1.3.0

## Naming conventions

The naming convention helps with consistent naming and identifying what each stack is.

### Symbols

\* = Any Character  
\+ = Number  
\# = Letter  
% = Letter or number  
" = Nato Alphabet  
? = Word  
() = Optional  
{} = Interpolation using camel casing

### Naming Table

| Stack      | Technical ID | Reference Name          | Official Name                | Example 1                               | Example 2                                |
| ---------- | ------------ | ----------------------- | ---------------------------- | --------------------------------------- | ---------------------------------------- |
| Devices    | D\#\#\#\#    | {any}                   | (Code) Delta " or D-\#\#\#\# | DZTDI - raspi - Delta Omega             | DHOLW - homeComputer - D-HOLW            |
| Servers    | S%%%%        | {serverFunction}Server  | (Code) Sierra " or S-%%%%    | S1452 - mngCaseiumServer - Sierra Alpha | S1352 - comSideToMainServer - Code S-135 |
| Programs   | P\#%%%       | {officialNameW/O"Code"} | (Code) ?(?-\*\*\*\*)         | PC133 - caesium - Code Caesium          | PRT02 - roamingTool - Roaming-Tool       |
| Components | C\+\+\+\+    | {functionType}          | ?(?-\*\*\*\*)                | C1508 - mainMenuIn - Main Menu          | C4587 - alertModalOut - Alert-Modal      |

## Types

Types hint at the purpose of the device, server or component and helps ensuring it is only doing one thing. This way there should't be any side effects.

|             | Short | Description                                                             | Used for             |
| ----------- | ----- | ----------------------------------------------------------------------- | -------------------- |
| Manage      | mng   | Accessing databases for read/write operations and return data           | Devices, Server      |
| Communicate | com   | Handling communication between two or more programs, servers or devices | Devices, Server      |
| Record      | rec   | Storing data of some kind and provide a way to display them             | Programs, Components |
| Inquire     | inq   | Displaying or generating data based on user input                       | Programs, Components |
| Input       | in    | Getting user input                                                      | Components           |
| Output      | out   | Displaying data only                                                    | Components           |
| Request     | req   | Get data, with no user input                                            | Components           |
| Report      | rep   | Post or modify data                                                     | Components           |

## Versioning

Use [Semantic Versioning](https://semver.org/), but for programs with no public API, that requirement is ignored.

When releasing a new version, there always needs to be a release note, added to the releases.md file.

## Base User Roles

The Base User Roles are a general way categorizing different levels of access. For each individual program, different names and sub levels can be used, but they all need to have a base role assigned, for the global eco system. They can also be thought of as global role identifiers or a broad category. Imagine a Cessna and Airbus A380, which can do different things, but are both categorized as fixed-wing aircraft.

The naming and structure of the sub-roles just need to fit for it's environment. A user can have multiple roles.

|           | Description                                                            | Intended for                                          |
| --------- | ---------------------------------------------------------------------- | ----------------------------------------------------- |
| Overwatch | Has admin privilege for all programs in the given sub-ecosystem        | IT-Department, Person in charge of deploying software |
| Admin     | Is allowed to manipulate settings for a given program and manage users | Team-Leaders, Project-Managers                        |
| Unit      | Can use program, within the limits set by an Admin                     | Endusers, Employees                                   |

## Required files

Different files are requiered, depending on what something does. Example files can be found in schema folder.

| File Name     | File Type   | Content                                                                     | Required for                 | If                    |
| ------------- | ----------- | --------------------------------------------------------------------------- | ----------------------------- | --------------------- |
| README        | .md         | Details of the structure (brief description, list of devices, servers, etc) | server, programs, components  | always                |
| release_notes | .md         | List of release notes, separated by a horizontal line                       | server, programs, components  | always                |
| features      | .md         | List of implemented and planed features, with short description             | programs, components          | always                |
| roles         | .json       | Detailed description of avaiable roles and their permissions                | programs                      | an account is needed  |
| LICENSE       | any         | Provide details about the license                                           | server, programs, components  | uses specific license |
| apis          | .md         | List of implemented and planed APIs, with short description                 | servers, programs, components | more than 5 APIs      |
| colors        | .sass, .css | Liste of colors, containing hex, rgba and hsla values                       | programs, components          | own colors are used   |

## Flowcharts

For a consistent design of flow charts, to portrait how a program works, there is a library in the schema folder. Besides that there is an overview of all elements.

Flow charts are made with [draw.io / diagrams.net](https://www.diagrams.net/). There is a desktop application, which can be downloaded from the [GitHub repository](https://github.com/jgraph/drawio-desktop)

## File Names

| File Type                                            | Casing Style                                                 | Example                       |
| ---------------------------------------------------- | ------------------------------------------------------------ | ----------------------------- |
| Files and Folders for a program, component or server | Best practice for that programming language, framework, etc. | refer to official style guide |
| Readme Files                                         | All uppercase                                                | README.md                     |
| Other Files                                          | All lowercase with snake casing                              | profile_icon.psd              |
| Other Folders                                        | First letter uppercase and snake casing, prefer one word     | Graphics, Icons_And_Logos     |
| Repositories                                         | Camel Casing                                                 | mngCaesiumServer              |
| License Files                                        | All uppercase                                                | LICENSE                       |
