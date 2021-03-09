# Guidelines v2.0.0

## **Definitions**

The code null standard refers to things with certain terms. The defintion of these are listed below.

### **Segment**

A segment describes the type of project. It is a collective term to identify with what you are dealing and dictates which kind of files are required.

### **Projects**

The most generic type, that can be used whenever there is no obvious other segment. For example: You work on a project thats not just about writing code for a server, but also managing reports while also designing a product.

### **Devices**

Devices are all specific physical things, like computers, routers, micro-controllers, that are part of a project. This excludes broader definitions. In the sense of code null standards, a device would be your own smartphone, but is not refering to all other smartphones that are the same model.

### **Servers**

In the code null standard a server is only thought of as the software part. It doesn't matter on what kind of computer or device it runs.

### **Programs**

Programs are all software that are used for a certain task and provide a user interface of some kind. They can be used without any further coding.

### **Components**

Components are just small parts of software, that can be used in multiple programs. While they can provide user interfaces, they cannot be used on their own.

### **Sub-Segements**

In case of a collection of multiple segments that are bundled as one, it is refered to as sub-segments. An example would be a component, that defines several other components, either to work together or to work independently from each other. This type is only implicitly given.

### **Documents**

Documents refer to texts, plans, flow charts, books and everything else that can be drawn or written.

## **Versioning**

---

It is recommended that you use either best practices for your specific programming language, framework, etc. or stick to code null versioning (CNV). What style is used, is to be specified in the README.

When releasing a new version, there always needs to be a release note, added to the releases.md file. If you should release a version, depends on your own judgement. Ultimately it should be reasonable for your project.

### **code null versioning**

The CNV provides a rather simple schema. It is based on [Semantic Versioning](https://semver.org/), but with uses a ruleset, that is applicable to a broader range of projects.

A version string has the following structure and only consists of numbers. The parts that are in brackets are optional. Every bracket pair can be combined with every other or be left out entirely. But what is inside must always be there. When using these, the meaning must be specified in the README. For that the following destructuring can be used.

Structure: (prefix)w.x.y.z(dot)(dash)(\*)(-S)

Destructured:

- prefix: A prefix like "v" to indicate that is a version number
- w: Use for major versions
- x: Use for smaller functional updates
- y: Use for bug fixes and code optimization that do not impact the functionality and security updates
- z: Use for small styling changes, typo fixes or minor code changes, that do not impact the functionality
- dot: optional dot for separating the next part
- dash: optional dash for separating the next part
- \*: can be a letter or number, to indicate any further changes
- \-S: The current stage of the project (alpha, pre-alpha, etc.)

#### **Rules**

The follwoing rules apply when changing the version number. While some points might appear logical, they are still explicitly named.

1. A version number must always go up
   - The same applies to letters if used
2. Increments are only allow in single stepts
   - E.g.: No skipping from 1.1.2.0 to 1.1.4.0
3. A project always starts at version 0.1.0.0
4. When increasing a part of a version number, all lower parts must be reset to 0
   - An increase in the stage must reset the version to 0.1.0.0
   - If it is the first complete release the first version starts at 1.0.0.0
5. The stage addtion must not be added or removed in the middle of versioning and be either present from the beginning or not at all
   - Exception: If you release a stable production ready version, the stage additon may be dropped
6. A release may contain multiple smaller changes
   - E.g.: a major release may contain bug fixes as well
7. A prefix must not change whatsoever and must be present from the very beginning or not at all
8. All versions with major version 1 or higher are considered production ready, if they have dedicated releases
   - Exception: If the stage is specified in the version string

### Use cases

The code null versioning can be used for the following things:

- Programs
- (REST) Servers
- Packages
- Components
- Documentation files
- Projects
- Websites
- Data Formats/Types (e.g.: .json files)
- Classes
- Schemas
- Interfaces
- Product Designs
- Plans, Flow Charts, etc.

#### **Increasing the version numbers**

The following guidelines will help you decide whether or not to change the version.

#### **Major (w)**

These are released when there was a lot of change in functionality. The comparison base is always the intial release of the previous major version. Example: You current version is 3.3.6.1. You are considering jumping to version 4.0.0.0, thus you compare the changes relative to version 3.0.0.0.

The following cases should always lead to a new major version:

- More than half of the relevant code, text, structure etc. was reworked/refactored
- The UI or design changed drastically (not just different colors, but a (completely) new layout)
- When overflowing from minor version when reaching 10 (3.9.5.0 would become 4.0.0.0 and not 3.10.0.0)
- Breaking changes in any sense were introduced (e.g.: a commonly used interface changed the structure and therefore a lot of other parts needed to be changed, the end user has to change things to keep using the product, code etc.)

If you ever get the feeling, that what you changed is a lot different from what you had before, it is recommended to make it a new major version, even if it is technically just a new minor version.

For on going projects, that do not have dedicated releases, but rather change over time in small steps, major version increases by overflowing from minor versions.

#### **Minor (x)**

These are released when you add new smaller functionality, other changes where made, that the end user can notice or a security issue was fixed.

The following cases should always lead to a new minor version:

- A new part was added in software (e.g.: new area in a program/website/blog, addtional APIs on a server, new attributes on a component, new class member)
- A new part was added in other cases (e.g.: new section in a document, new arrangment on a floorplan, second handle for a pot))
- Some parts were moved to a different position (e.g.: file input is now at the top instead bottom, section b now comes before section a, the arrangement of buttons on a remote control changed)
- A security issue was fixed

#### **Optimization (y)**

This part is increased whenever bug fixes, changes in the (code) structure or other optimization are released. The word "bug" is not strictly meant for coding projects, but also refers to everything else that leads to unwanted behaviour or consequences.

The following cases should always lead to a new optimization version:

- One or multiple bugs were fixed
- Code was refactored/optimized, without changing the functionality (e.g.: a function was rewritten to be more efficient)
- Optimization in a product functionality

Some examples for what is considered a bug outside of coding projects:

- The design of a mug leads to dripping when drinking
- A rule in a rulebook was too losely defined and creates a loophole
- In a document a word was used wrongly and changes the meaning of the sentence
- In an Excel table a formular misses some parantheses that result in a different output
- On a website an old link is still present
- On a floor plan the wrong dimensions were used for the placement of an item

#### **Style (z)**

Style updates only include very minor changes, that do not impact the product or project in a meaningful way.

The following cases should always lead to a new style version:

- spelling mistakes were fixed
- A few sentences were rewritten for better readabillity
- The name of a few variables changed (just the naming and only if it doesn't impact other parts)
- Some styles or colors changed a bit
- Existing texts, strings, buttons etc. were formatted differently
- Details on a design changed

#### **Project Stage**

The project stage addition changes whenever you change from one stage to another. Every change in that part results in a reset of all previous parts. If the project is still in active developement (pre-alpha, alpha, beta, etc.) you must keep this addtion, until the first stable production ready release.

There are no specific rules, for when to move from one stage to another. It is recommended to define in advance which features or contents must be present to consider it a new development stage.

For non-coding projects this part might not be relevant, but if used it must follow the same rules,

#### **Optional Parameters**

These optional parameters can be anything that makes sense for that project. For further differentiation you can add numbers or letters, seperated by a dash or a dot. They still need to follow the basic rule of always increasing and resetting when a higher part is increased. However in which cases these change, can be freely defined. Those rules must be documented in the README.

#### **Version Examples**

The following is an example of a versioning history for a component using the CNV. This is not a complete history and just highlights some examples.

| Current Version | Next Version | Changes                                                                                             |
| --------------- | ------------ | --------------------------------------------------------------------------------------------------- |
| v0.1.0.0        | v0.1.0.0     | Work just started on the project                                                                    |
| v0.1.0.0        | v0.1.1.0     | After implementing the most basic inputs, a few bugs needed to be fixed                             |
| v0.1.1.0        | v0.2.0.0     | More logic was added, some other bugs were found and fixed                                          |
| v0.2.3.2        | v0.3.0.0     | Even more logic was added                                                                           |
| v0.3.9.2        | v0.4.0.0     | Yet another functionality change was made, increasement leads to overflow to the next major version |
| v0.4.6.8        | v1.0.0.0     | Component is production ready and released for use                                                  |
| v1.0.0.0        | v1.0.0.1     | A typo was fixed, nothing else was changed yet                                                      |
| v1.0.0.1        | v1.1.0.0     | A security issue was fixed                                                                          |

Here are some more example of how a version string might look.

| Version String  | Refers to                                                                                               |
| --------------- | ------------------------------------------------------------------------------------------------------- |
| 0.2.4.5         | A non-production ready version, still in early development                                              |
| 0.2.4.5-alpha   | A non-production ready version, in alpha stage                                                          |
| 0.2.4.5.f-alpha | A non-production ready version, in alpha stage, with custom f addition                                  |
| 2.4.0.5         | The second major production ready version, with some additions in functionality and small style changes |
| v2.4.0.5        | Same as previous, just with a prefix                                                                    |
| d2.4.0.5        | Same as previous, just with a different prefix, that could indicate that it belongs to a document       |
| v2.4.0.5-abc    | Production ready release, with addiotional part, that could indicate numerous things                    |
| v2.4.0.5.a.c    | Production ready release, with two addiotional parts, that could indicate numerous things               |

---

## **Types**

---

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
| Collection  | col   | A collection of components                                              | Components           |

## **Base User Roles**

---

The Base User Roles are a general way categorizing different levels of access. For each individual program, different names and sub levels can be used, but they all need to have a base role assigned, for the global eco system. They can also be thought of as global role identifiers or a broad category. Imagine a Cessna and Airbus A380, which can do different things, but are both categorized as fixed-wing aircraft.

The naming and structure of the sub-roles just need to fit for it's environment. A user can have multiple roles.

|           | Description                                                            | Intended for                                          |
| --------- | ---------------------------------------------------------------------- | ----------------------------------------------------- |
| Overwatch | Has admin privilege for all programs in the given sub-ecosystem        | IT-Department, Person in charge of deploying software |
| Admin     | Is allowed to manipulate settings for a given program and manage users | Team-Leaders, Project-Managers                        |
| Unit      | Can use program, within the limits set by an Admin                     | Endusers, Employees                                   |

## **Required files**

---

Different files are required, depending on what something does. Example files can be found in the [examples](src/examples) folder. Note that there are multiple READMEs, one for every segment. The name in a real project should still be README.md.

| File Name     | File Type         | Content                                                                     | Required for                  | If                     | Place in |
| ------------- | ----------------- | --------------------------------------------------------------------------- | ----------------------------- | ---------------------- | -------- |
| README        | .md               | Details of the structure (brief description, list of devices, servers, etc) | server, programs, components  | always                 | root     |
| release_notes | .md               | List of release notes, separated by a horizontal line                       | server, programs, components  | always                 | /docs    |
| features      | .md               | List of implemented and planed features, with short description             | programs, components          | always                 | /docs    |
| roles         | .json             | Detailed description of avaiable roles and their permissions                | programs                      | an account is needed   | /docs    |
| LICENSE       | any               | Provide details about the license                                           | server, programs, components  | it needs license       | root     |
| apis          | .md               | List of implemented and planed APIs, with short description                 | servers, programs, components | more than 5 APIs       | /docs    |
| components    | .md               | List of implemented and planed components, with short description           | component collections         | more than 3 components | /docs    |
| colors        | .sass, .css, .txt | Liste of colors, containing hex, rgba or hsla values                        | programs, components          | own colors are used    | /docs    |

## **Flowcharts**

---

For a consistent design of flow charts to portrait how a program works, there is a library in the schema folder. Besides that there is an overview of all elements.

Flow charts are made with [draw.io/diagrams.net](https://www.diagrams.net/). There is a desktop application, which can be downloaded from the [GitHub repository](https://github.com/jgraph/drawio-desktop)

## **Naming conventions**

---

The naming convention helps with consistent naming and identifying what each segement is. All conventions are overriden by best practices if necessary.

### **Symbols**

| Symbol   | Meaning                                                                                                       |
| -------- | ------------------------------------------------------------------------------------------------------------- |
| \*       | Any Character                                                                                                 |
| \+       | Number                                                                                                        |
| \#       | Letter                                                                                                        |
| %        | Letter or number                                                                                              |
| "        | Nato Alphabet                                                                                                 |
| ?        | Word or Combination of words                                                                                  |
| ()       | Optional                                                                                                      |
| {}       | Interpolation, prefer camel casing if not spacing is allowed                                                  |
| ident    | Abbriviation or identifier of the company or creator, to produce unique ids; must be at least four characters |
| (-flags) | Additional optional characters, separated by a dash, maximum of four                                          |

### **Segment**

| Segment      | Short ID (all uppercase)      | Public ID                      | Official Name                | Example                                                    |
| ------------ | ----------------------------- | ------------------------------ | ---------------------------- | ---------------------------------------------------------- |
| Projects     | PR\#\#%%                      | {ident}{projectname}           | ?(-flags)                    | PRCN00 - alpaCodeNullOrganization - code null organization |
| Devices      | D\#\#\#\#                     | {ident}{any}                   | (Code) Delta " or D-\#\#\#\# | DZTDI - alpaRaspi - Delta Omega                            |
| Servers      | S%%%%                         | {ident}{serverFunction}Server  | (Code) Sierra " or S-%%%%    | S1452 - alpaMngCaseiumServer - Sierra Alpha                |
| Programs     | P\#%%%                        | {ident}{officialNameW/O"Code"} | (Code) ?(-flags)             | PC133 - alpaCaesium - Code Caesium                         |
| Components   | C\+\+\+\+                     | {ident}{functionType}          | ?(-flags)                    | C1508 - alpaMainMenuIn - Main Menu-2x                      |
| Sub-Segments | {t-id}\_{segment prefix}%(%%) | {ident}{functionType}          | ?(-flags)                    | C0001_C1 - alpaCheckboxIn - code null checkbox             |
| Documents    | DOC%%%%                       | {ident}Doc{any}                | ?(-flags)                    | DOCGL02 - alpaDocGuideline - Guidelines                    |
| Websites     | WEB%%%%                       | {ident}Web{any}                | ?(-flags)                    | WEBSHP0 - alpaWebShop - Air Shop                           |
| Products     | PROD%%%%                      | {ident}Prod{any}               | ?(-flags)                    | PRODM17 - alpaProdMugNumber17 - Mug Nr. 17                 |

### **File Names**

| File Type                                            | Casing Style                                                 | Example                       |
| ---------------------------------------------------- | ------------------------------------------------------------ | ----------------------------- |
| Files and Folders for a program, component or server | Best practice for that programming language, framework, etc. | refer to official style guide |
| Readme Files                                         | All uppercase                                                | README.md                     |
| Other Files                                          | All lowercase with snake casing                              | profile_icon.psd              |
| Other Folders                                        | snake casing, prefer one word                                | Graphics, Icons_And_Logos     |
| Repositories                                         | Camel Casing                                                 | mngCaesiumServer              |
| License Files                                        | All uppercase                                                | LICENSE                       |

### **Abreviations, etc.**

Abbreviations should be all uppercase, when used in a text.

## **File Strucure**

---

A project with code null standard should have the following base file structure. This example containts all optional files, which can be left out if they are not rquired.

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
- **resrouces**(optional)
  - addtional resources that should be provided
- **project**
  - content of your actual project goes here (source code, etc.)
