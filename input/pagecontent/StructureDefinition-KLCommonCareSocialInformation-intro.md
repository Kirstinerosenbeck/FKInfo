<!-- StructureDefinition-KLCommonCareSocialInformation-intro.md {% comment %}
*****************************************************************************************
*                            WARNING: DO NOT EDIT THIS FILE                             *
*                                                                                       *
* This file is generated by SUSHI. Any edits you make to this file will be overwritten. *
*                                                                                       *
* To change the contents of this file, edit the original source file at:                *
* ig-data\input\pagecontent\StructureDefinition-KLCommonCareSocialInformation-intro.md  *
*****************************************************************************************
{% endcomment %} -->
## Scope and usage
The CommonCareSocialInformation may be instatiated whenever information about the citizen is recorded, under the headings defined by FFB Themes (plus a few of the subthemes, which are not conditions), Areas (FSIII områder), General Information (FSIII generelle oplysninger). For each heading, a new instanse of CommonCareSocialInformation is used. CommonCareSocialInformation  is used in Danish municipalities. For FSIII areas, in special cases, a severity may be recorded together with or instead of the text. This should be recorded, using the profile CommonCareSocialInformationSeverity, which may be associated with this profile using the hasMember attribute.


### Conversions between Danish information model and FHIR-profile

Nedenstående tabel oversætter mellem de attributter der er defineret i den fælleskommunale informationsmodel (FKI), definerer kort den enkelte attribut på dansk og specificere hvilke af FHIR-profilens atributter der skal bruges til specifikation af indholdet

{:class="grid"}
|   FKI-attribut      | Definition        | FHIR  |
| ------------- |-------------| -----|
|oplysningskode|Klasse der udtrykker, hvilket fagligt emneområde, oplysningen tilhører. |Observation.code.coding.code|
|oplysningstekst|oplysningens tekst|Observation.stringvalue|
|oplysningssubjekt|den borger som oplysningen omhandler|Observation.subject|
|oplysningskontakt|Den kontakt hvor oplysningsaktiviteten har fundet sted.|Observation.encounter|
|oplysningsansvarlig|Den fagperson, der er ansvarlig for oplysningen|Observation.performer|
|oplysningsordre|Den henvendelse/henvisning, der har udløst at oplysningsaktiviteten er igangsat|Observation.basedOn|
|oplysningstid|Det tidspunkt hvor oplysningen er fremkommet, vurderet eller dokumenteret|Observation.effective.datetime|
|oplysningssværhedsgrad|sværhedsgraden af de udfordringer som indhentede informationer observationer og vurderinger har belyst, organiseret under faglige emneområder|Observation.hasmember|