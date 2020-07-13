<!-- StructureDefinition-KLCommonCareSocialServiceRequest-intro.md {% comment %}
*******************************************************************************************
*                             WARNING: DO NOT EDIT THIS FILE                              *
*                                                                                         *
* This file is generated by SUSHI. Any edits you make to this file will be overwritten.   *
*                                                                                         *
* To change the contents of this file, edit the original source file at:                  *
* ig-data\input\pagecontent\StructureDefinition-KLCommonCareSocialServiceRequest-intro.md *
*******************************************************************************************
{% endcomment %} -->
## Scope and usage
The CommonCareSocialServiceRequest may be instatiated to signify that a request for a service is recieved in a Danish Municipality. A ServiceRequest may either be a request or a referal (Henvendelse/Henvisning), but the use of the model should reflect this. A referal, where a GP or a hospital has already decided that the service is required should have the sending organisation as the requester, and if no further information and/or authorisation from the municipality is needed, the intent-attribute value is 'order'. This is e.g. true for GP's orders to acute nursing teams, here the ServiceRequest is the documentation that the interventions that the nurses perfrom are authorized. When a citizen or next-of-kin request a service from the municipality, the requester is the municipality practitioner that talks to the citizen or next -of-kin, and who is responsible for its communication to the right parties in the municipality. The subjectConsentToLiasing extension is used in FFB to signify whether the citizen knows about the service request or not. It should not be stated unless it is explicitely known, and only for FFB.  

### Conversions between Danish information model and FHIR-profile

Nedenstående tabel oversætter mellem de attributter der er defineret i den fælleskommunale informationsmodel (FKI), definerer kort den enkelte attribut på dansk og specificere hvilke af FHIR-profilens atributter der skal bruges til specifikation af indholdet

{:class="grid"}
|   FKI-attribut      | Definition        | FHIR  |
| ------------- |-------------| -----|
|henvendelsesHenvisningAnsvarlig|Den som har ansvar for henvendelsen/henvisningen|ServiceRequest.requester|
|henvendelsesHenvisningFra|Klasse der angiver, hvilken instans, der har henvist eller har henvendt sig.|ServiceRequest.extension: RequesterType|
|henvendelsesHenvisningsårsag|Beskrivelse af årsagen til henvisningen/henvendelsen|ServiceRequest.reasonCode.text|
|henvendelsesHenvisningsstatus|Klasse der udtrykker status for henvendelsen|ServiceRequest.status|
|henvendelsesHenvisningsHensigt|Klasse der udtrykker hensigten med henvendelsen|ServiceRequest.intent|
|henvendelsesHenvisningsIndsats|Klasse der udtrykker, hvilken type kommunal indsats/ydelse der anmodes om.|ServiceRequest.code|
|henvendelsesHenvisningsAnmodetIndsats|Klasse der udtrykker, hvilken kommunal indsats/ydelse der anmodes om.|Servicerequest.orderDetail|
|henvendelsesHenvisningsSubjekt|Den borger som henvisningen/henvendelsen vedrører|ServiceRequest.subject|
|henvendelsesHenvisningstid|Det tidspunkt hvor henvisning/henvendelsen er forfattet af den ansvarlige|ServiceRequest.authoredOn|
|borgerIndforståetMedHenvisningHenvendelse|Klasse der angiver om borger er indforstået med henvendelsen|SeviceRequest.extension: SubjectConsentToLiaising|
|henvendelsesHenvisningsbegrundelse|Den borgertilstand, der er grund til at en instans henvender sig til kommunen.|SeviceRequest.reason|
|henvendelseHenvisningsårsagsreference|Et klassificeret opfølgningsresultat, der er baggrund for at borger revisiteres.|ServiceRequest.reasonReference|