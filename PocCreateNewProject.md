# Proof Of Concept : Create New Project in NB 6.0 #
by: daniel widyanto a.k.a kunilkuda


## Prequisities ##
  * Tinyos 2.x (including nesc, tinyos-tools, gnu make, avr-gcc or msp-gcc, etc) is fully installed in the workstation. [Refer to the TinyOS website for the installation](http://www.tinyos.net/tinyos-2.x/doc/html/install-tinyos.html).


---


## Creating New Project ##
### Creating New Module ###
  1. Create new module from NB: New Project->Netbeans Modules->Module
  1. Name it as **PocCreateNewProject**, set as standalone module, set as main project
  1. Use this code name base: org.netbeans.modules.poccreatenewproject, and keep the rest untouched (Module Display Name, Localizing Bundle, XML Layer).

### Creating Dummy NesC Template ###
> The nesC template (taken from 

&lt;tinyos-dir&gt;

/app/Null) is going to be used as NB template when user create new nesC project.
  1. Create new C/C++ application project in NB:New Project->C/C++->C/C++ Application
  1. Name it as: **NescTemplate**, keep Makefile as Project Makefile Name, and DO NOT set it as **MAIN PROJECT** (this is just the nesc template).
  1. Put all of 

&lt;tinyos-dir&gt;

/app/Null files inside the new created project directory (replace NB's Makefile with TinyOS', **DO NOT MODIFY** the nbproject/ directory).

### Insert nesC Template as New Project Template ###
  1. Go to **PocCreateNewProject**
  1. Create new project template: Right click->New->Project Template..
  1. Select **NescTemplate** as Project
  1. Use this value for the template form
    * Template name: NesC
    * Display name: NesC Application
    * Category: C/C++
    * Project: **PocCreateNewProject**
    * Package: org.netbeans.modules.poccreatenewproject
  1. NB will zip the template, and create forms (in Java file) to be modified.


---


## Testing The Module ##
  1. Right click on **PocCreateNewProject**->Insert/Reload in Target Platform
  1. Select File->New Project->C/C++->NesC Application
  1. Generate project
  1. The TinyOS Null application **should be replicated** in the test project directory.
  1. The TinyOS project **is not compileable** under NB (yet).