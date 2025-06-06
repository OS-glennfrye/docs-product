---
summary: OutSystems 11 (O11) introduces an Asynchronous Logging API that enables non-persistent, queued database logging for errors, records, and request events.
tags: asynchronous programming, logging, performance optimization, application monitoring, error handling
locale: en-us
guid: 3f292aa4-1be7-4699-8231-0d465c90297d
app_type: traditional web apps, mobile apps, reactive web apps
platform-version: o11
figma:
audience:
  - backend developers
  - full stack developers
  - platform administrators
  - architects
outsystems-tools:
  - service studio
coverage-type:
  - remember
---

# Asynchronous Logging API


The Asynchronous Logging API provides actions to perform the following asynchronously:

* insert records into the database
* register request events of your applications

The record or request event gets added to a queue. Then it is processed asynchronously and added to the database.

The asynchronous queue is non-persistent. This means that in case of a system failure, pending records and request events get lost.

To use this API, simply reference the AsynchronousLogging module in your application.

## Summary

Action | Description
---|---
[LogError](<#LogError>) | Asynchronously inserts a error into the database. Errors are kept in a queue and inserted into the database in bulk after a short period.
[LogRecord](<#LogRecord>) | Asynchronously inserts a record into the database. Records are kept in a queue and inserted into the database in bulk after a short period.
[LogRequestEvent](<#LogRequestEvent>) | Asynchronously logs a request event. The events are kept in a queue and inserted in bulk after a short period.

## Actions

### LogError { #LogError }

Asynchronously inserts a error into the database. Errors are kept in a queue and inserted into the database in bulk after a short period. Note that the queue is non-persistent.

*Inputs*

Instant
:   Type: DateTime. Mandatory.  
    Date and time when the error occurred.

RequestKey
:   Type: Text.  
    The GUID that identifies the request. Use the Request_GetKey action of the PlatformRuntime API to get this value.

ModuleName
:   Type: Text. Mandatory.  
    Name of the module where the event occurred.

Message
:   Type: Text. Mandatory.  
    A text with the error main message.

Detail
:   Type: Text.  
    A text with the error details.

### LogRecord { #LogRecord }

Asynchronously inserts a record into the database. Records are kept in a queue and inserted into the database in bulk after a short period. Note that the queue is non-persistent.

*Inputs*

Record
:   Type: Object. Mandatory.  
    The record you want to save to the database, converted to Object type. Use the ToObject built-in function for the conversion.

### LogRequestEvent { #LogRequestEvent }

Asynchronously logs a request event. The events are kept in a message queue and inserted in bulk after a short period.

*Inputs*

Instant
:   Type: DateTime. Mandatory.  
    Date and time when the event occurred.

RequestKey
:   Type: Text. Mandatory.  
    The GUID that identifies the request. Use the Request_GetKey action of the PlatformRuntime API to get this value.

RequestEventName
:   Type: Text. Mandatory.  
    Name of the event.

ModuleKey
:   Type: Text. Mandatory.  
    Unique identifier of the module where the event occurred. Use the GetEspace action with the GetOwnerEspaceIdentifier() built-in function to get this information.

ModuleName
:   Type: Text. Mandatory.  
    Name of the module where the event occurred. Use the GetEspace action with the GetOwnerEspaceIdentifier() built-in function to get this information.

ApplicationKey
:   Type: Text. Mandatory.  
    Unique identifier of the application where the event occurred. Query the ‘Application’ system entity to get this information.

ApplicationName
:   Type: Text. Mandatory.  
    Name of the application where the event occurred. Query the ‘Application’ system entity to get this information.

RequestEventDetails
:   Type: Text.  
    A text with event details in JSON format. It is a regular JSON object with the fields ‘Key’ and ‘Value’.


