# Guidelines v2.0.0.0

## **Definitions**

The code null standard refers to things with certain terms. The definition of these are listed below.

### **Segment**

A segment describes the type of project. It is a collective term to identify with what one is dealing and dictates which kind of files are required.

### **Devices**

Devices are all specific physical things, like computers, routers, micro-controllers, that are part of a project. This excludes broader definitions. In the sense of code null standards, a device would be your own smartphone, but is not referring to all other smartphones that are the same model.

### **Servers**

In the code null standard a server is only thought of as the software part. It doesn't matter on what kind of computer or device it runs.

### **Programs**

Programs are all software that are used for a certain task and provide a user interface of some kind. They can be used without any further coding.

### **Components**

Components are just small parts of software, that can be used in multiple programs. While they can provide user interfaces, they cannot be used on their own.

### **Sub-Segments**

In case of a collection of multiple segments that are bundled as one, it is referred to as sub-segments. An example would be a component, that defines several other components, either to work together or to work independently from each other. This type is only implicitly given.

### **Short ID**

The short ID is used for internal references and ease of use. For example it can be added to a file or folder name, to indicate to which project it belongs to.

### **Public ID**

The public ID is there to distinguish your project from those of others, in case it is made public. It can also be used as a reference name in other projects. A public ID should be unique.

## **Versioning**

It is recommended to use either best practices for your specific programming language, framework, etc. or stick to code null versioning (CNV). What style is used, is to be specified in the README.

When releasing a new version, there always needs to be a release note, added to the releases.md file. If a new version should be released, depends on the judgement of the project members or owner. Ultimately it should be reasonable for the project.

To easily link to the CNV, it was separated from this document and can be found in the [resources folder](src/resources/cn_versioning.md).

## **Types**

Types hint at the purpose of the device, server or component and helps ensuring it is only doing one thing. This way there shouldn't be any side effects.

Data can be of any kind and can mean stored data from a database, e-mails, images and so on.

|             | Short | Description                                                             | Used for             |
| ----------- | ----- | ----------------------------------------------------------------------- | -------------------- |
| Manage      | mng   | Manage data in some way and return it if necessary                      | Devices, Server      |
| Communicate | com   | Handling communication between two or more programs, servers or devices | Devices, Server      |
| Serve       | srv   | Serve data only                                                         | Devices, Server      |
| Record      | rec   | Storing data of some kind and provide a way to display them             | Programs, Components |
| Inquire     | inq   | Displaying or generating data based on user input                       | Programs, Components |
| Input       | in    | Getting user input                                                      | Components           |
| Output      | out   | Displaying data only                                                    | Components           |
| Request     | req   | Get data, with no user input                                            | Components           |
| Report      | rep   | Post or modify data                                                     | Components           |
| Collection  | col   | A collection of components                                              | Components           |

## **Base User Roles**

The Base User Roles are a general way categorizing different levels of access. For each individual program, different names and sub levels can be used, but they all need to have a base role assigned, for the global eco system. They can also be thought of as global role identifiers or a broad category. Imagine a Cessna and Airbus A380, which can do different things, but are both categorized as fixed-wing aircraft.

The naming and structure of the sub-roles just need to fit for it's environment. A user can have multiple roles.

|           | Description                                                            | Intended for                                          |
| --------- | ---------------------------------------------------------------------- | ----------------------------------------------------- |
| Overwatch | Has admin privilege for all programs in the given sub-ecosystem        | IT-Department, Person in charge of deploying software |
| Admin     | Is allowed to manipulate settings for a given program and manage users | Team-Leaders, Project-Managers                        |
| Unit      | Can use program, within the limits set by an Admin                     | End users, Employees                                  |

## **Required files and folders**

Different files and folders are required, depending on what something does. Example files can be found under [resources/examples](resources/examples), templates can be found under [resources/templates](resources/templates).

| File Name        | File Type         | Content                                                                             | Required for                  | If                                | Place in |
| ---------------- | ----------------- | ----------------------------------------------------------------------------------- | ----------------------------- | --------------------------------- | -------- |
| README           | .md               | Details of the structure (brief description, list of devices, servers, etc)         | server, programs, components  | always                            | root     |
| release_notes    | .md               | List of release notes, separated by a horizontal line                               | server, programs, components  | always                            | /docs    |
| features         | .md               | List of implemented and planed features, with short description                     | programs, components          | always                            | /docs    |
| roles            | .json             | Detailed description of available roles and their permissions                       | programs                      | an account is needed              | /docs    |
| LICENSE          | any               | Provide details about the license                                                   | server, programs, components  | it needs license                  | root     |
| apis             | .md               | Documentation of exposed APIs, with short description                               | servers, programs, components | more than 3 APIs or complex types | /docs    |
| component_apis   | .md               | Documentation of exposed attributes, methods and data types, with short description | components                    | complex data types are needed     | /docs    |
| excomponent_apis | .md               | Documentation of exposed attributes, methods and data types, with short description | component collection          | always                            | /docs    |
| colors           | .sass, .css, .txt | List of colors, containing hex, rgba or hsla values                                 | programs, components          | own colors are used               | /docs    |

## **Flowcharts**

For a consistent design of flow charts to portrait how a program works, there is a library in the schema folder. Besides that there is an overview of all elements.

Flow charts are made with [draw.io/diagrams.net](https://www.diagrams.net/). There is a desktop application, which can be downloaded from the [GitHub repository](https://github.com/jgraph/drawio-desktop)

## **Naming conventions**

The naming convention helps with consistent naming and identifying what each segment is. All conventions are overridden by best practices if necessary.

### **Symbols**

| Symbol | Meaning                                                                                                       |
| ------ | ------------------------------------------------------------------------------------------------------------- |
| \*     | Any Character                                                                                                 |
| \+     | Number                                                                                                        |
| \#     | Letter                                                                                                        |
| %      | Letter or number                                                                                              |
| ()     | Optional                                                                                                      |
| {}     | Interpolation, prefer camel casing if not spacing is allowed                                                  |
| ident  | Abbreviation or identifier of the company or creator, to produce unique ids; must be at least four characters |

### **Segments**

| Segment      | Short ID (all uppercase)      | Public ID                      | Example                      |
| ------------ | ----------------------------- | ------------------------------ | ---------------------------- |
| Devices      | D\#\#\#\#                     | {ident}{any}                   | DZTDI - codnRaspi            |
| Server       | S%%%%                         | {ident}{serverFunction}Server  | S1452 - codnMngTimePodServer |
| Programs     | P\#%%%                        | {ident}{officialNameW/O"Code"} | PC133 - codnTimePod          |
| Components   | C\+\+\+\+                     | {ident}{function}({any}){type} | C1912 - codnModalSAMOut      |
| Sub-Segments | {t-id}\_{segment prefix}%(%%) | {ident}{functionType}          | C0001_C1 - codnCheckboxIn    |

### **File Names**

| File Type                                            | Casing Style                                                 | Example                       |
| ---------------------------------------------------- | ------------------------------------------------------------ | ----------------------------- |
| Files and Folders for a program, component or server | Best practice for that programming language, framework, etc. | refer to official style guide |
| Readme Files                                         | All uppercase                                                | README.md                     |
| Other Files                                          | All lowercase with snake casing                              | profile_icon.psd              |
| Other Folders                                        | snake casing, prefer one word                                | Graphics, Icons_And_Logos     |
| Repositories                                         | Camel Casing                                                 | mngCaesiumServer              |
| License Files                                        | All uppercase                                                | LICENSE                       |

### **Abbreviations, etc.**

Abbreviations should be all uppercase, when used in a text.

## **File Structure**

A project with code null standard should have the following base file structure. This example contains all optional files, which can be left out if they are not required.

### **root**

- README`.md`
- LICENSE
- **docs**
  - release_notes`.md`
  - features`.md`
  - roles`.json`
  - apis`.md`
  - components`.md`
  - colors`.scss`/`.css`/`.txt`
- **resources**(optional)
  - additional resources that should be provided
- **project**
  - content of your actual project goes here (source code, etc.)
