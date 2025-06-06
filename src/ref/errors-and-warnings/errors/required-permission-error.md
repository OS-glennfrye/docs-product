---
summary: Explore common permission errors in OutSystems 11 (O11) related to module updates and user provider settings.
locale: en-us
guid: f1dd1b03-de58-453d-a537-f17b73c72595
app_type: traditional web apps, mobile apps, reactive web apps
platform-version: o11
figma:
tags: permissions, security, publishing, user management, service center administration
audience:
  - platform administrators
  - full stack developers
  - frontend developers
outsystems-tools:
  - service studio
  - service center
coverage-type:
  - unblock
---

# Required Permission Error

The `Required Permission` error is issued in the following situation:

* `You are not allowed to update your Personal Area in module '<consumer module>'. Please contact your Service Center administrator.`

    You no longer have the Publish security level on the Consumer module you've selected to run your module.

    Retry the Run operation and if you still get this message, contact your Service Center administrator to grant permissions.

* `You are not allowed to use '<module>' as User Provider module. Please contact your Service Center administrator.`

    You no longer have the Reference security level on the module you've selected to as User Provider.

    Contact your Service Center administrator to grant permissions.
