### Patient Handover Journey

Overview of the process - 

introduction to the technical side of the process

#### Patient Handover Journey Current 

![Patient Handover Current](framework/Patient Journey.png)
<br clear="all" />

#### Patient Handover Journey Future Options

1. The Referral Request becomes a two way process which can include:
* Acceptance or rejected of a handover
* Updating a handover request
* Cancelling a handover request

2. Workflow Monitoring is enhanced by the ability to send real time ADT notifications which complement the referral event triggers. These include
* Notification admit - the start of care provision
* Notification discharge -  the end of care provision

3. National Event Messaging Service can used as a Pub/Sub service to distribute the Referral and ADT notifications.

4. Directory of Service will be reused by NHS 999 for Endpoint discovery. 'Do they already do this?'

![Patient Handover Future](framework/Patient Journey Future.png)
<br clear="all" />

### Handover Message Specifications

Majority of these exchanges are verbal and/or document clinically focused exchanges (paper or pdf) and are used to transfer the care of the patient from one care provider to another. The technical specifications used in UEC are also focused on the exchange clinical documents:

* [NHS 111 -> NHS 999 Handover](https://data.developer.nhs.uk/dms/IUC-3.0-RC1/Domains/messages.html) - Integrated Urgent Care Ambulance Request (REPC_MT200001GB02) 
This is used to transfer the care of patient from the NHS 111 service to the NHS 999 Service
* [NHS 111 -> NHS 111](https://data.developer.nhs.uk/dms/IUC-3.0-RC1/Domains/messages.html) - Integrated Urgent Care Report (POCD_MT200001GB02)
This is used to transfer the care of the patient to another NHS 111 service
* [NHS 999 -> ED](https://theprsb.org/standards/ambulancehandover/) - AMBULANCE HANDOVER TO EMERGENCY CARE STANDARD
This is used to transfer the care of the patient from NHS 999 to an Emergency Department


![UEC Message Flows](framework/UEC Referral Letter Flow.jpg)
<br clear="all" />

### Handover General Structure

The clinical model is a technical structure which a coherent set of information that is a statement of healthcare information, including clinical observations and services. It is often called a structured document to distinguish it from other documents formats such as html, pdf or word. 
There are two main document standards in use within NHS:

* Clinical Document Architecture (CDA)
  * XML standard based on HL7 version 3
  * Used by NHS 111 Integrated Urgent Care Ambulance Request and Integrated Urgent Care Report
* FHIR Document 
  * JSON/XML standard based on HL7 FHIR.
  * Being used for NHS 999 AMBULANCE HANDOVER TO EMERGENCY CARE STANDARD 
  * Used by NHS Emergency Departments for Discharge Letters

The two standards are related and consist of structured elements such as 
* Patient - Which contains the Patient demographics
* Encounter - Which contains basic details of the clinical encounter such as start and end times, problem, service type, etc
* ReferralRequest - Details of what action is required, by whom and who created the request.

The sections are html based and may reference structured clinical items such as Observations. Both Clinical Formats can easily be converted to html pages (see below) and so can be used with providers at different stages of maturity and different capabilities.

![Clinical Document](framework/Clinical Document.png)
<br clear="all" />