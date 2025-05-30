---
summary: Explore solutions for the 'Invalid Error Handler Flow' error in OutSystems 11 (O11) when error handler flows intersect main paths.
locale: en-us
guid: 0f83bb7e-3cc8-4134-938b-9f9194175dc7
app_type: traditional web apps, mobile apps, reactive web apps
platform-version: o11
figma:
tags: error handling, debugging, application development, outsystems platform, exception handling
audience:
  - mobile developers
  - frontend developers
  - full stack developers
outsystems-tools:
  - service studio
coverage-type:
  - unblock
---

# Invalid Error Handler Flow Error

The `Invalid Error Handler Flow` error is issued in the following situation:

* `Flow path of error handler '<error handler>' can't cross main path or other in flow '<flow>'`
  
    The flow path of the error handler is coming across the execution of the screen or the action flow.

    Change the flow of the error handler to not come across the screen or the action flow.
