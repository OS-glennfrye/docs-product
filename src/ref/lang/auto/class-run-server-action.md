---
helpids: 30107
summary: Execute server-side logic with input and output parameters using the Run Server Action tool in OutSystems 11 (O11).
locale: en-us
guid: f5811e56-3206-4621-a31a-74da90160dd2
app_type: traditional web apps, mobile apps, reactive web apps
platform-version: o11
figma: https://www.figma.com/file/eFWRZ0nZhm5J5ibmKMak49/Reference?node-id=842:1136
tags: server actions, business logic, action flow, input parameters, output parameters
audience:
  - mobile developers
  - frontend developers
  - full stack developers
outsystems-tools:
  - service studio
coverage-type:
  - remember
topic:
  - server-actions-when-use
---

# Run Server Action


Executes a Server Action that runs logic on the server. Server Actions usually encapsulate logic that implements the business rules of your application.

You can use the Run Server Action element in the logic flow of actions such as:

* Client Actions
* Data Actions
* other Server Actions
* Automatic Activities
* methods of exposed REST APIs and SOAP Web Services
* Preparations and Screen Actions (only available in Traditional Web Apps)

When the Server Action you wish to run has input parameters, you provide their values in the properties of the Run Server Action element. This is also called **providing the arguments** for running the Server Action.

![Screenshot showing the properties of the Run Server Action element in Service Studio](images/run-server-action-properties-ss.png "Run Server Action Properties")

When the Server Action you wish to run has output parameters, you can use them in the logic that follows the Run Server Action element. There must be a logical path from the Run Server Action element to the place where the output parameter is used.

In the following example, we used the **Valid** output parameter of the **ValidateAPIKey** Server Action in an expression:

![Example of using the Valid output parameter from ValidateAPIKey Server Action in an expression](images/run-server-action-use-output-ss.png "Using Server Action Output")

## How to use the Run Server Action tool

1. In the action flow where you want to run the Server Action, drag the **Run Server Action** tool and drop it in the action flow.

    ![Dragging the Run Server Action tool into the action flow in Service Studio](images/run-server-action-drag-ss.png "Drag Run Server Action")

    Alternatively, open the **Logic** tab, expand the **Server Actions** folder, and drag the Server Action you want to run and drop it in the action flow.  
    In this case, skip the next step because you already selected the desired Server Action.

    ![Dragging a Server Action from the Logic tab into the action flow in Service Studio](images/run-server-action-drag-2-ss.png "Drag Server Action from Logic Tab")

1. In the pop-up window, select the Server Action that you want to run from the **Server Actions** folder in the tree, and click **Select**.

    ![Selecting a Server Action from the Server Actions folder in the pop-up window](images/run-server-action-select-ss.png "Select Server Action")

1. Provide the arguments for the Run Server Action element by filling in the values in the properties editor. You must enter a value at least for the mandatory input parameters of the Server Action.

    ![Screenshot showing the properties of the Run Server Action element in Service Studio](images/run-server-action-properties-ss.png "Run Server Action Properties")

1. If the Server Action has output parameters, you can use them in the logic flow after the Run Server Action element.

    ![Example of using the Valid output parameter from ValidateAPIKey Server Action in an expression](images/run-server-action-use-output-ss.png "Using Server Action Output")

## Properties

<table markdown="1">
<thead>
<tr>
<th>Name</th>
<th>Description</th>
<th>Mandatory</th>
<th>Default value</th>
<th>Observations</th>
</tr>
</thead>
<tbody>
<tr>
<td title="Name">Name</td>
<td>Identifies an element in the scope where it is defined, like a screen, action, or module.</td>
<td>Yes</td>
<td></td>
<td></td>
</tr>
<tr>
<td title="Action">Action</td>
<td>Action with logic to run on the server.</td>
<td>Yes</td>
<td></td>
<td>It might be necessary to specify additional action input arguments.</td>
</tr>
</tbody>
</table>

