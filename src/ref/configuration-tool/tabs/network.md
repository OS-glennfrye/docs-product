---
summary: Explore network configuration options in OutSystems 11 (O11), including IP address settings and internal network adjustments.
locale: en-us
guid: 8a4e8da5-fdb0-4112-a474-c1781f35d12c
app_type: traditional web apps, mobile apps, reactive web apps
platform-version: o11
figma:
tags: network configuration, service center, ip configuration, security, deployment
audience:
  - frontend developers
  - full stack developers
  - platform administrators
  - infrastructure managers
outsystems-tools:
  - service center
coverage-type:
  - remember
---

# Network tab

The **Network** taballows you to clear the current internal network settings, and allows you to define the IP address the front-end server registers in the deployment controller service.

![Screenshot of the Network tab in the Configuration Tool](images/network-tab-ct.png "Network tab")

## Internal Network section

When developing your applications, you can set resources such as web flows (groups of screens), and web services to be available only within your internal network. This configuration is [defined in Service Center](../../../security/configure-internal-network.md).

However, you may inadvertently define an Internal Network configuration that blocks you from accessing Service Center altogether. In that case, use the **Clear Internal Network Settings** button to clear all internal network settings currently defined.

<div class="warning" markdown="1">

**Warning:** When you clear your internal network settings, your internal applications are accessible from any origin.

</div>

## Front-end registration

You can configure the IP address that the front-end server registers in the deployment controller service. This setting is useful for servers with multiple network adapters, allowing you to select on which network the OutSystems services communicate with each other.

Configuration  |  Description  |  Default value  
---|---|---  
Local IP Address | The list displays all IPs available for the front-end server you are configuring. | `(automatic)`
