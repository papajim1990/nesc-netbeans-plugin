# Proof Of Concept : Create New Project Category in NB 6.0 #
by: daniel widyanto a.k.a kunilkuda

## Prequisities ##
  * Tinyos 2.x (including nesc, tinyos-tools, gnu make, avr-gcc or msp-gcc, etc) is fully installed in the workstation. [Refer to the TinyOS website for the installation](http://www.tinyos.net/tinyos-2.x/doc/html/install-tinyos.html).
  * PocCreateNewProject is created.


---


## Creating New Project Category ##
  * Edit layer.xml file in org.netbeans.modules.poccreatenewproject
  * Change:

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE filesystem PUBLIC "-//NetBeans//DTD Filesystem 1.1//EN" "http://www.netbeans.org/dtds/filesystem-1_1.dtd">
<filesystem>
  <folder name="Templates">
    <folder name="Project">
      <folder name="Native">
        <file name="NesCProject.zip" url="NesCProject.zip">
          <attr name="SystemFileSystem.localizingBundle" stringvalue="org.netbeans.modules.poccreatenewproject.Bundle"/>
          <attr name="instantiatingIterator" methodvalue="org.netbeans.modules.poccreatenewproject.NesCWizardIterator.createIterator"/>
          <attr name="instantiatingWizardURL" urlvalue="nbresloc:/org/netbeans/modules/poccreatenewproject/NesCDescription.html"/>
          <attr name="template" boolvalue="true"/>
        </file>
      </folder>
    </folder>
  </folder>
</filesystem>
```

> Into:

```
<!DOCTYPE filesystem PUBLIC "-//NetBeans//DTD Filesystem 1.1//EN" "http://www.netbeans.org/dtds/filesystem-1_1.dtd">
<filesystem>
  <folder name="Templates">
    <folder name="Project">
      <folder name="NesC"> <!-- Change project category to NesC -->
        <file name="NesCProject.zip" url="NesCProject.zip">
          <attr name="SystemFileSystem.localizingBundle" stringvalue="org.netbeans.modules.poccreatenewproject.Bundle"/>
          <attr name="instantiatingIterator" methodvalue="org.netbeans.modules.poccreatenewproject.NesCWizardIterator.createIterator"/>
          <attr name="instantiatingWizardURL" urlvalue="nbresloc:/org/netbeans/modules/poccreatenewproject/NesCDescription.html"/>
          <attr name="template" boolvalue="true"/>
        </file>
      </folder>
    </folder>
  </folder>
</filesystem>
```


---


## Testing The Module ##
  1. Right click on **PocCreateNewProject**->Insert/Reload in Target Platform
  1. Select File->New Project
  1. **NesC project category should appear** in Project category
  1. **NesCProject.zip shoud appear** under **NesC** project category