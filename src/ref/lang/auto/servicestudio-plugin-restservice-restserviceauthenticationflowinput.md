---
summary: OutSystems 11 (O11) automates input parameter configuration for REST API authentication.
helpids: 30061
locale: en-us
guid: 7fbaa379-bf8c-43e8-8352-f320768a330d
app_type: traditional web apps, mobile apps, reactive web apps
platform-version: o11
figma:
tags: rest api, basic authentication, parameter configuration, service studio, documentation
audience:
  - mobile developers
  - frontend developers
  - full stack developers
outsystems-tools:
  - service studio
coverage-type:
  - remember
---

# Input Parameter - REST Authentication

Input parameter of the exposed REST API authentication action (Username or Password). Both Username and Password input parameters are added/removed automatically by Service Studio when configuring the REST API to use Basic authentication/Custom authentication, respectively.  

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
<td title="Description">Description</td>
<td>Text that documents the element.</td>
<td></td>
<td></td>
<td>Useful for documentation purpose.<br/>The maximum size of this property is 2000 characters.</td>
</tr>
<tr>
<td title="Type">Data Type</td>
<td>The data type of the input parameter.</td>
<td>Yes</td>
<td></td>
<td></td>
</tr>
<tr>
<td title="IsMandatory">Is Mandatory</td>
<td>Set to Yes to require for a value to be set.</td>
<td>Yes</td>
<td>Yes</td>
<td></td>
</tr>
<tr >
<th colspan="5">Advanced</th>
</tr>
<tr>
<td title="DefaultValue">Default Value</td>
<td>Initial value of this element. If undefined, the default value of the data type is used.</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

