---
summary: Learn how to implement and design Process Callback actions in OutSystems 11 (O11) to validate and control process execution flows.
locale: en-us
guid: c903f266-1cdc-45fb-9609-188a79440359
app_type: traditional web apps, mobile apps, reactive web apps
platform-version: o11
figma:
tags: business rules, process flows, callback actions, process validation, process design
audience:
  - mobile developers
  - frontend developers
  - full stack developers
outsystems-tools:
  - service studio
coverage-type:
  - apply
topic:
  - using-callbacks
---

# Using Process Callback Actions

When designing the process flow of your process, you can add business rules to validate the execution of your process. This allows you to block or quit the process execution if a specified condition is not verified. This behavior is implemented through **Process Callback actions**.


## Add a Process Callback Action

1. From the **Processes** tab, right-click the process element and select **Add Callback Action**.

1. Select one of the **On Process ...** actions.

    ![Screenshot showing how to add a Process Callback Action in the Processes tab](images/add-callback-action-ss.png "Adding a Process Callback Action")

1. Design the behavior of the action.

    You can design the business rules for the following available process callback action:

    * **On Process Start**: this action is executed before a **Process** starts its execution.

You can also design activity callback actions at the process level. This allows you to move the common business rules in the callbacks of several process activities to a single place at the process level.
