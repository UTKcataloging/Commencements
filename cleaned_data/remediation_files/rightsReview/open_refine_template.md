# OpenRefine Template for Commencements Remediation

---

## Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```

## Row Template

```
<mods>
<identifier type="pid">{{cells['PID'].value}}</identifier>
<identifier type="filename">{{cells['identifier'].value}}</identifier>
{{if(isBlank(cells['title'].value), '', '<titleInfo><title>' + cells["title"].value + '</title></titleInfo>')}}
{{if(isBlank(cells['title_supplied'].value), '', '<titleInfo supplied="yes"><title>' + cells['title_supplied'].value + '</title></titleInfo>')}}
{{if(isBlank(cells["abstract"].value),'', '<abstract>' + cells['abstract'].value + '</abstract>')}}
{{'<originInfo>' + if(isBlank(cells['year'].value), '', '<dateCreated>' + cells['year'].value + '</dateCreated>') + if(isBlank(cells['dateCreated_edtf'].value), '', '<dateCreated encoding="edtf" keyDate="yes">' + cells['dateCreated_edtf'].value + '</dateCreated>') + '<publisher>' + cells['publisher'].value + '</publisher></originInfo>'}}
<physicalDescription><form authority="aat" valueURI="{{cells['form_URI'].value}}">{{cells['form'].value}}</form></physicalDescription>
{{if(isBlank(cells['subject'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject_URI'].value + '"><topic>' + cells['subject'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject2'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject2_URI'].value + '"><topic>' + cells['subject2'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject3'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject3_URI'].value + '"><topic>' + cells['subject3'].value + '</topic></subject>')}}
<subject><topic>{{cells['subject4'].value}}</topic></subject>
<language><languageTerm type="text" authority="iso639-2b">English</languageTerm></language>
<typeOfResource>text</typeOfResource>
<classification authority="lcc">{{cells['classification'].value}}</classification>
<relatedItem displayLabel="Project" type="host"><titleInfo><title>{{cells['digital_collection'].value}}</title></titleInfo></relatedItem>
<location><physicalLocation valueURI="http://id.loc.gov/authorities/names/no2014027633">University of Tennessee, Knoxville. Special Collections</physicalLocation></location>
<recordInfo><recordContentSource valueURI="http://id.loc.gov/authorities/names/n87808088">University of Tennessee, Knoxville. Libraries</recordContentSource><recordOrigin>Created and edited in general conformance to MODS Guidelines (Version 3.5).</recordOrigin></recordInfo>
<accessCondition type="use and reproduction" xlink:href="{{cells['rights_URI'].value}}">{{cells['rights'].value}}</accessCondition>
</mods>
```

## Row Separator

**LEAVE BLANK**

## Suffix

```
</modsCollection>
```