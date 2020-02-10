

This bit covers the technical process flow

### Fire and Forget

The existing system .....saf asf asd saf some text some text some text afdsfas a  df adsg adfgdf dffdg fdfdag fdfdg dfgdfagadgliug weuiweiurqiuiwcriruyiurhewcjkrhewjckrwhjrkwehcrkwj end of long sentence.

<div>
<p style="text-align:center;"><img src="framework/Patient Referral Sequence Diagram.png" alt="Tasks" title="Patient Referral Sequence Diagram"></p>
<br clear="all" />
<br />
</div>

#### Patient Referral

[Patient Referral](MessageDefinition-patient-referral.html)

  
|----------------------------|-----|-----|
| Resource                   | Min | Max |
|----------------------------|-----|-----|
| MessageHeader              |  1  |  1  |
| ReferralRequest            |  1  |  1  |
| Encounter                  |  1  |  1  |
| Patient                    |  1  |  1  |
| Composition (Referral Letter)   |  1  |  1  |
| QuestionaireResponse (Triage)   |  0  |  1  |
|----------------------------|-----|-----|
{: .grid }

### Exchange of Fire

A negotiated referral

<div>
<p style="text-align:center;"><img src="framework/Patient Referral plus Response Patient Referral Sequence Diagram.png" alt="Tasks" title="Patient Referral plus Response Patient Referral Sequence Diagram" style="width:50%"></p>
<br clear="all" />
<br />
</div>

#### Response Patient Referral

[Response Patient Referral](MessageDefinition-response-patient-referral.html) 

|----------------------------|-----|-----|
| Resource                   | Min | Max |
|----------------------------|-----|-----|
| MessageHeader              |  1  |  1  |
| ReferralRequest            |  1  |  1  |
|----------------------------|-----|-----|
{: .grid }

#### Modify Patient Referral

[Modify Patient Referral](MessageDefinition-modify-patient-referral.html)

|----------------------------|-----|-----|
| Resource                   | Min | Max |
|----------------------------|-----|-----|
| MessageHeader              |  1  |  1  |
| ReferralRequest            |  1  |  1  |
| Encounter                  |  1  |  1  |
| Patient                    |  1  |  1  |
| Composition (Referral Letter)   |  1  |  1  |
| QuestionaireResponse (Triage)   |  0  |  1  |
|----------------------------|-----|-----|
{: .grid }

#### Cancel Patient Referral

[Cancel Patient Referral](MessageDefinition-cancel-patient-referral.html)

|----------------------------|-----|-----|
| Resource                   | Min | Max |
|----------------------------|-----|-----|
| MessageHeader              |  1  |  1  |
| ReferralRequest            |  1  |  1  |
| Encounter                  |  1  |  1  |
| Patient                    |  1  |  1  |
|----------------------------|-----|-----|
{: .grid }


### Contact Reporting (ADT)

This partly exists, the XXXReport is sent to the Repeat Caller Service
<div>
<p style="text-align:center;"><img src="framework/Patient Referral plus ADT Notifications Sequence Diagram.png" alt="Tasks" title="Patient Referral plus ADT Notifications Sequence Diagram" style="width:75%"></p>
<br clear="all" />
<br />
</div>

#### Notification Admit 

Pathway started 

Message Definition [Notification Admit](MessageDefinition-notification-admit.html)

Example [Notification Admit](Bundle-notification-admit.html)

|----------------------------|-----|-----|
| Resource                   | Min | Max |
|----------------------------|-----|-----|
| MessageHeader              |  1  |  1  |
| Encounter                  |  1  |  1  |
| Patient                    |  1  |  1  |
|----------------------------|-----|-----|
{: .grid }

#### Notification Discharge

Message Definition [Notification Discharge](MessageDefinition-notification-discharge.html)

Example [Notification Discharge](Bundle-notification-discharge.html)

|----------------------------|-----|-----|
| Resource                   | Min | Max |
|----------------------------|-----|-----|
| MessageHeader              |  1  |  1  |
| Encounter                  |  1  |  1  |
| Patient                    |  1  |  1  |
|----------------------------|-----|-----|
{: .grid }

### Encounter Discovery

During the triage process a decision is made to refer the patient care to another provider. A service is selected by consulting the NHS 111 Discovery Service, the response contains technical delivery information which is used to sed the clinical document is sent to the provider.

<div>
<p style="text-align:center;"><img src="framework/NHS 111 Triage Overview Sequence Diagram.jpg" alt="Tasks" title="NHS 111 Triage Overview Sequence Diagram"></p>
<br clear="all" />
<br />
</div>

### Service/Endpoint Discovery

Allows responder to indentify services 

[Directory of Service](https://developer.nhs.uk/apis/uec-tech-standards/clinical_decision_support_api.html)


<div>
<p style="text-align:center;"><img src="framework/Triage and Referral.jpg" alt="Tasks" title="Triage and Referral" ></p>
<br clear="all" />
<br />
</div>

### Use of Pub/Sub (NEMS)

[National Events Management Service](https://developer.nhs.uk/apis/ems-beta/)



