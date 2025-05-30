---
summary: OutSystems 11 (O11) integrates AWS Key Management Service for HIPAA-compliant encryption and decryption of PHI through its Cryptography Services app.
tags: hipaa compliance, encryption, aws key management service, phi encryption, cryptography
locale: en-us
guid: 259aca31-dc2a-4eb1-8d5c-e322cefe5e66
app_type: traditional web apps, mobile apps, reactive web apps
platform-version: o11
figma: https://www.figma.com/file/iBD5yo23NiW53L1zdPqGGM/Developing-an-Application?type=design&node-id=4397%3A521&mode=design&t=GF97AOUqsRf9tsAh-1
audience:
  - mobile developers
  - frontend developers
  - full stack developers
  - platform administrators
outsystems-tools:
  - service studio
coverage-type:
  - understand
topic:
  - data-encryption
---

# Implement encryption and decryption for HIPAA compliance

When you subscribe to the OutSystems Cloud HIPAA offering your environments will include an app that you can reference to encrypt and decrypt PHI - **Cryptography Services**.

In its core, AWS Key Management Service provides a secure and resilient service to create and manage cryptographic keys.

The Cryptography Services app interfaces with the Key Management Service (KMS) abstracting from the complexity of having and managing a KMS. 

![Diagram illustrating the Cryptography Services app interfacing with AWS Key Management Service for encrypting and decrypting PHI in OutSystems Cloud HIPAA offering](images/hipaa-crypto-diag.png "Cryptography Services Diagram")

It exposes actions that work with the KMS to encrypt and decrypt PHI. Those are divided into two groups of actions, depending on whether you need to search on the encrypted data: **actions for searchable attributes** and **actions for unsearchable attributes**.

## About searchable and unsearchable data

Searchable data allows you to perform searches while unsearchable data does not. For example, you may encrypt both `email address` and `blood type`, but you only want `blood type` to be searcheable. This means, you can design a screen that filters a search by `blood type` but not by `email address`.

Searchable data encryption uses unsalted, predictable encryption, meaning that the same plaintext input with the same key  always produces the same ciphertext. While this approach is less secure, it allows for easier searching.

On the other hand, unsearchable data encryption employs salted encryption, where additional random data, known as a "salt," is added to the plaintext. This ensures that even with the same plaintext and key, the resulting ciphertext will be different each time, providing stronger security at the cost of searchability.

## Actions for searchable attributes

These actions generate an unsalted encryption using the same key for all records that use the same **IndexType**. The same text results in the same cyphertext allowing apps to search within encrypted values without having to decrypt all records first. They shouldn't be used for combinations of patient-identity and medical information together.

GetIndexKey
:   Returns the Id of a key that's mapped to an **IndexType**. The IndexType is used to identify an attribute. You define a string that uniquely identifies the attribute. The Cryptography Services saves this relation with the **KeyId** and the **IndexType**. It retrieves a new **KeyId** if the **IndexType** doesn't exist. Otherwise, it retrieves the existing **KeyId** mapped for that **IndexType**.

EncryptIndexText
:   Encrypts searchable attributes.

DecryptIndexText
:   Decrypts searchable attributes.


## Actions for unsearchable attributes

These actions use the same underlying cryptographic processes with two additional protections: it's salted with the **EntityId** input and the keys are rotated periodically.
You'll need to save the relation of the record with it's salt and the KeyId. You can do this by creating an Entity to hold this mapping.
The rotation period of the keys is defined by the site property **GenericKeysExpirationInMinutes** of the Cryptography Services module. You can change this value in Service Center.

GetEntityKey
:   Returns the Id of a key. Due to the rotation, you'll need to to use this action whenever you create or update records.

EncryptEntityText
:   Encrypts the text of unsearchable attributes using a KeyId and a salt (EntityId).

DecryptEntityText
:   Decrypts into text/plain the cyphered text of unsearchable attributes using a KeyId and a salt (EntityId).


Check the following articles for detailed guides of the implementation of:

* [Encrypting data for HIPAA compliance](encrypt-data-hipaa.md)
* [Decrypting HIPAA compliant data](decrypt-data-hipaa.md)
* [Search encrypted data](search-encrypted.md)

To know more about HIPAA in the OutSystems Cloud check [HIPAA compliant apps in the OutSystems Cloud](https://success.outsystems.com/Support/Security/HIPAA_compliance_-_how_OutSystems_can_help#HIPAA_compliant_apps_in_the_OutSystems_Cloud).
