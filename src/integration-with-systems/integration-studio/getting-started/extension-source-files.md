---
locale: en-us
guid: b45e7737-81b3-441d-9baf-641f310c262d
app_type: traditional web apps, mobile apps, reactive web apps
platform-version: o11
figma: https://www.figma.com/design/jSgZ0l0unYdVymLxKZasno/Extensibility-and-Integration?node-id=3734-5&t=5Xy7sf3amevfps10-1
summary: Learn how OutSystems 11 (O11) automates the generation of extension source files for streamlined development in Integration Studio.
tags: ide usage, reactive web apps, tutorials for beginners, .net development, extension customization
audience:
  - backend developers
  - full stack developers
  - frontend developers
outsystems-tools:
  - integration studio
coverage-type:
  - understand
topic:
  - legacy-systems-integration
  - custom-code-integration
---

# Extension Source Files

Once the extension is [created](<../extension-life-cycle/extension-create.md>), Integration Studio automatically generates, according to the [definition](<../extension-life-cycle/extension-define.md>) of the extension elements, the necessary template files for the development bootstrap of that extension. Once these templates are generated, the source files listed below are added as resources of your extension and you can start coding the behavior of your extension actions.

<div class="info" markdown="1">

Template files are the files needed to generate the extension assembly without any custom code, without any code written by the developer. These files are implicitly generated by Integration Studio in the following operations: Create a new Extension, Update the Extension Source Code, or Compare with Template.

</div>

The extension source files are stored in the file system in the `Extension` folder, under the Source folder in the corresponding sub-folder. You can check them in the [Resources](<../../../ref/integration-studio/resources-tree.md>) tree.

## .NET Source files

By default, your extension has the following source files, stored under the `Source\NET` folder:

* Project files called `<ExtensionName>.sln`, `<ExtensionName>.csproj`.

* Extension implementation files:

    * Actions are implemented in the  `<ExtensionName>.cs` file, which contains a .NET method for each action defined by your extension: the method name is `Mss<ActionName>` and parameters names are `ss<ParameterName>`.

        ![Warning icon indicating important information about .NET method signatures in the extension source files](images/warning.png "Warning Icon") This file contains the signature of the methods that correspond to the actions exposed by your extension. You must not change these signatures. Any action, either [defined](<../managing-extensions/action-add.md>) in Integration Studio or [imported](<../managing-extensions/net-assembly-import-action.md>) from an assembly, must be defined in this file.

        Actions are declared in the `Interface.cs` file in the same way as explained above for `<ExtensionName>.cs` file.

    * Entities are declared in the `Entities.cs` file, which contains a .NET structure for each entity defined in by your extension: the structure name is `EN<EntityName>EntityRecord` and member names are `ss<AttributeName>`.

    * Record Lists are declared in the `RecordLists.cs` file, which contains a .NET class for each record list definition used in your actions: the class name is `RL<RecordListDefinition>RecordList` and a set of methods are generated to manage the record list.

    * Records are declared in the `Record.cs` file, which contains a .NET structure for each record definition used in your actions: the structure name is `RC<RecordDefinition>Record` and a set of methods are generated to manage the record.

    * Structures are declared in the `Structures.cs` file, which contains a .NET structure for each structure defined in your extension: the structure name is `ST<EntityName>Structure` and member names are `ss<AttributeName>`.

    These files are automatically generated by Integration Studio, during the [Update Source Code](<../extension-life-cycle/extension-update-source-code.md>) operation, and you should not change them in the .NET IDE.

* The `Bin2` folder contains the DLL files associated with your extension and their dependencies, namely: the `OutSystems.Nss<ExtensionName>.dll` which is the main DLL of your extension; the `OutSystems.HubEdition.RuntimePlatform.dll`, which is an internal DLL necessary to Integration Studio.

* The `Obj` folder contains the temporary files required by the IDE for building the .NET solution.

## Properties of the Source Files

The extension source files are added as resources of the extension with the following properties:

* **Name**: Name of the resource as explained above.
* **Last Modified**: Date and time when the resource was last modified since the last save.
* **Deploy Action**: For the files stored under the `Binaries` folder, this property has the value `Copy to Binaries directory`. For the rest of the files, this property has the value `Ignore`.

For more information about the Deploy Action property, see [Resource Properties](<../../../ref/integration-studio/element-property/resource.md>).

