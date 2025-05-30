---
summary: Learn how to define extension entities in OutSystems 11 (O11) to utilize external database tables effectively.
locale: en-us
guid: c5e5c6fd-fba7-4be6-ba09-d1b028c8a1c1
app_type: traditional web apps, mobile apps, reactive web apps
platform-version: o11
figma:
tags: extension entities, database integration, entity management, user permissions, external database
audience:
  - mobile developers
  - frontend developers
  - full stack developers
outsystems-tools:
  - service studio
  - service center
coverage-type:
  - apply
---

# Define Extension Entities

Once you have created your extension, simply define the **entities** exported by the extension. These entities allow you to use database tables that exist outside OutSystems.

<div class="info" markdown="1">

To publish a new extension that contains entities, your OutSystems user must have the "Allow External Entities" permission. Check with the Service Center administrator for a list of your permissions.

</div>

To add an entity to your extension, do one of the following operations:

* [Add the entity](<entity-add.md>) manually to the extension.

* Import the entity definition from a database, through the [Import Entities from Database](<entity-import-from-database.md>) wizard.
