---
summary: OutSystems 11 (O11) enables IT user management through a role-based permission model, supporting both simple and complex security policies.
tags: it user management, role-based permissions, security policies, authentication, team management
locale: en-us
guid: be9622e0-f844-42a6-8ca2-b4a486cfc4e0
app_type: traditional web apps, mobile apps, reactive web apps
platform-version: o11
figma: https://www.figma.com/file/rEgQrcpdEWiKIORddoVydX/Managing%20the%20Applications%20Lifecycle?node-id=267:21
audience:
  - platform administrators
  - full stack developers
outsystems-tools:
  - lifetime
coverage-type:
  - understand
topic:
  - it-user-management-in-lt
---

# Manage IT Users

<div class="info" markdown="1">

This section applies to **IT users** like OutSystems developers and Administrators.  
To learn more about managing the **end users** of your OutSystems applications, check [End User Management](../../user-management/end-user-manage/accessing-users.md).

</div>

OutSystems allows you to define the permissions of IT users using a [role-based permission model](about-permission-levels.md). This model enables you to set up the permissions of your IT users for simple or complex security policy needs. You can:

* Configure authentication across systems for IT users by using an [external authenticator provider](use-an-external-authentication-provider.md).
* Set up the permissions of a small team using only the built-in default roles, Developer and Administrator.
* [Create additional roles](create-an-it-role.md#create-a-new-role) to better control the different permission levels of a larger team.
* [Use teams](create-an-it-team.md) to manage an enterprise-grade security policy, where you have many applications and users.
* [Grant or revoke permissions to users for specific applications](grant-it-roles-for-a-specific-application.md) without using teams.

Manage your IT Teams in the **USER MANAGEMENT** area of your LifeTime console (`https://<lifetime_env>/lifetime`).

![Screenshot of the USER MANAGEMENT area in the OutSystems LifeTime console](images/intro-1.png "LifeTime Console User Management")

To manage IT teams, you must be an infrastructure manager.
