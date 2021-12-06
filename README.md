Instituto Superior Técnico, Universidade de Lisboa

**Network and Computer Security**

# Project Topics

_Important note: the security aspects, both functional and assurance ones, are the essential points where you should focus your work and will be the main metrics to be considered in the grading. In the designed and proposed solutions, user interface concerns are secondary._

----

## 1. Web payments

Consider a _merchant website_ with areas of different access levels for anonymous users, registered users, and store administrators.
The site must be secure against the threats like XSS and SQL injection and/or other attacks.
The solution should consider all tiers explicitly, including: web, application, database.
Remember that *tier* is a physical separation in the architecture whereas *layer* may be just a logical separation.
The network topology should be adequately designed for protection with security in mind.

The web site should allow Payment Initiation Services (PIS), inspired by the Europen Payment Services Directive (PSD2).
These services help to initiate a payment from the consumer's account on a _bank_ to the merchant's account by creating an interface to bridge both accounts, filling in the information needed for the bank transfer (amount of the transaction, account number, message) and informing the store of the transaction.

**Suggested references:**

- <https://en.wikipedia.org/wiki/Payment_Services_Directive>
- <https://www.bportugal.pt/en/page/payment-services-under-psd2>

----

## 2. Smartphone as a security token

The smartphone is an indispensable digital companion for many people in their daily lives.
This work should leverage its _proximity_ to the user as part of an increased security solution.

The smartphone can be used in new ways for:
- _Authentication_ - for example, the user should have the phone with himself to answer an authentication challenge posed by a web application to perform two-factor authentication;
the phone can also make use of existing _biometric_ sensors;
- _Authorization_ - for example, the user should confirm on the phone an access to an important resource in a web application;
- _Delegation_ - the user can grant temporary permissions to a nearby user, using a protocol over Wi-Fi, Bluetooth, NFC, or QR Codes.

In all of the examples above, the solution should be designed with a good balance between security and usability, with special consideration for the _pairing_ of devices and for the regular interaction.
The security solution to propose will have to be implemented in a working prototype, running in a mobile operating system, suitable for demonstration of the capabilities.

**Suggested references:**

- [Duo SDK](https://duo.com/product/every-application/supported-applications/apis) -- two-factor authentication API _(there are others)_
- [KeePass Plugins](https://keepass.info/help/v2/plugins.html) -- open-source password vault
- [Bitwarden](https://github.com/bitwarden) -- open-source password manager

----

## 3. Remote document access with ransomware protection

Collaborative applications allow groups of users to create and edit documents remotely.
These documents are regularly synchronized between personal devices and the remote servers.
In these applications, a user, owner of the document, can select contributors which have access to the document.
Documents should not be accessed by unauthorized parties.
If an attacker accesses the servers storing the documents he must not be able to view the documents and if he tries to edit any document, there must be a way to detect the illegal modifications.

A _ransomware attack_ happens when a system is breached and the attacker encrypts the user files and asks for a ransom to provide the decryption key.
If properly implemented, recovering the files without the decryption key is an intractable problem.
Also, the identification of the attackers can be difficult with the use of cryptocurrencies like BitCoin.  
Organizations must have backups, with version history, to allow recovery in the case of ransomware attacks.

In this topic, the solution should allow documents to be shared over a public network in a secure fashion.
It should allow authenticated users to access local and remote files in a transparent way.
Data confidentiality must be assured even in the case where an attacker gains physical access to the data storage devices.
Illegal modification of the documents by unauthorized users must be detected.
The document system should resist ransomware attacks.

**Suggested references:**

- [Nextcloud](https://github.com/nextcloud) -- client-server software for creating and using file hosting services
- [Syncthing](https://docs.syncthing.net/) -- file synchronization tool

----

## 4. Proofs of location for smart cars

Future autonomous vehicles will need to support several cooperative services to achieve _safety_ and _security_ on real life scenarios.
The vehicles will need to use not only their own sensors but share and use sensor data from others, achieving _Collective Perception Services_.
This will ensure that data will arrive ahead of its needs and that safety standards are attained.
For example, the vehicle could be equipped with Bluetooth or Wi-Fi and use signal detection to ``see'' pedestrians and bycicles that could, otherwise, remain unseen.

One of the needed services will be vehicles location: each vehicle will need to proof their own location, using sensors but also using data from other witnesses.
Passing cars or another road infrastructure can be used for that purpose.
For example, to prove the presence at a parking spot or at a charging station.

We suggest that the following terminology is used:
a _prover_ makes a claim of location at a specific time with self-collected evidence;
a _witness_ endorses the claim and add its own evidence;
the _verifier_ analyzes all the available evidence and makes a decision to accept the claim, or not.

In this project, you should use one of the proposed simulators, or another one that you consider appropriate to the context, to implement a simulated system of proof of location for vehicles (cars) using IEEE 802.11p and IEEE 1609.4 DSRC/WAVE network layers on a highway.
You can also consider the use of Road Side Units (RSU).

**Suggested references:**

- [SureThing Core Data](https://github.com/inesc-id/SureThing_Core_Data) -- Example location proof data definitions in Protobuf format
- [Survey of the Connected Vehicles](https://ieeexplore.ieee.org/abstract/document/8058008)
  - [SUMO](https://www.eclipse.org/sumo/) -- Simulation of Urban MObility
  - [CARLA](https://carla.org/) -- Open-source simulator for autonomous driving research.
  - [Veins](https://veins.car2x.org/features/) -- The open source vehicular network simulation framework.
  - [OMNeT++](https://omnetpp.org/) -- Discrete Event Simulator

----

## 5. Contact tracing

In this topic, we consider device tracking using their hardware identifiers.
Each mobile device has one or more hardware identifiers that are broadcast in local networks, namely the Wi-Fi adapter MAC addresses.
The same happens with Bluetooth.
A typical system architecture has a data aggregation server (on the cloud), a set of scan servers that send periodic reports of sighted devices, and a query client.
Keeping record of these identifiers and associating them with users can help track the iteration between devices and their users, but can also become a severe privacy violation as we can know of a user's whereabouts and daily routines.

The goal of the scenario is to develop a service for smartphones to assess the interaction between devices/people in order to track potential COVID-19 contamination, while maintaining the _privacy_ of the users.
The system should allow:  
i) the device owner to inform others that he is infected (using a code given by the health authority) or  
ii) to be informed that he was in contact with someone infected.  
In case of ii) the user should be able to get the information where this contact occurred and for how long.

**Suggested references:**

- [D3PT](https://github.com/DP-3T/documents) -- Decentralized Privacy-Preserving Proximity Tracing
- [Apple and Google Privacy-Preserving Contact Tracing](https://covid19.apple.com/contacttracing) -- joint documentation from the two leading smartphone OS providers

----

## 6. Medical test records

Health care institutions gather and store sensitive information from patients.
The information systems should allow fine-grained and contextualized access to the records to the relevant staff, like Doctors and Nurses.
Other staff with different data access needs include: clinical assistants (take care of ward housekeeping), patient services assistants (bring meals and drinks), porters (take care of patient lifting and transport), volunteers (help with fundraising and ward visits), and ward clerks (staff the ward reception desks).

One of the relevant types of data stored are _test results_.
Some of the medical tests can be performed inside a _hospital lab_, but in many cases, tests are done in _partner labs_, that have a distinct infrastructure, remote from the infrastructure of the hospital, that need to be interconnected.
Also, the medical test data has to be archived in a way such that its authenticity can be verified later, if necessary.

It is mandatory that the solution externalizes the security policy with a policy language, like XACML, with separate policy authoring and enforcement points, and different parts of the patient record can be accessed by different people and in different contexts.  
To demonstrate the advantage of this separation, the solution should have a _Normal_ mode of operation and a _Pandemic_ mode, where the rules for data access are significantly different.
The switch between modes should be done with changes to the policy documents but without changes to the application code.

**Suggested references:**

- [RFC2753](https://tools.ietf.org/html/rfc2753) -- Framework for Policy-based Admission Control
- [XACML](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=xacml#other) -- security policy language _(there are other languages)_
  - [XACML library](https://github.com/wso2/balana) -- example XACML implementation _(there are other libraries)_

----

[SIRS Faculty](mailto:meic-sirs@disciplinas.tecnico.ulisboa.pt)
