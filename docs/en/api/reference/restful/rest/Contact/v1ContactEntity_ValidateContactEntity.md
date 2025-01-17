---
title: POST Contact/Validate
uid: v1ContactEntity_ValidateContactEntity
generated: true
---

# POST Contact/Validate

```http
POST /api/v1/Contact/Validate
```

Check that entity is ready for saving, return error messages by field.








## Request Headers

| Parameter Name | Description |
|----------------|-------------|
| Authorization  | Supports 'Basic', 'SoTicket' and 'Bearer' schemes, depending on installation type. |
| X-XSRF-TOKEN   | If not using Authorization header, you must provide XSRF value from cookie or hidden input field |
| Content-Type | Content-type of the request body: `application/json`, `text/json`, `application/xml`, `text/xml`, `application/x-www-form-urlencoded`, `application/json-patch+json`, `application/merge-patch+json` |
| Accept         | Content-type(s) you would like the response in: `application/json`, `text/json`, `application/xml`, `text/xml`, `application/json-patch+json`, `application/merge-patch+json` |
| Accept-Language | Convert string references and multi-language values into a specified language (iso2) code. |
| SO-Language | Convert string references and multi-language values into a specified language (iso2) code. Overrides Accept-Language value. |
| SO-Culture | Number, date formatting in a specified culture (iso2 language) code. Partially overrides SO-Language/Accept-Language value. Ignored if no Language set. |
| SO-TimeZone | Specify the timezone code that you would like date/time responses converted to. |
| SO-AppToken | The application token that identifies the partner app. Used when calling Online WebAPI from a server. |

## Request Body: contactEntity 

Entity to be checked for errors. 

| Property Name | Type |  Description |
|----------------|------|--------------|
| ContactId | Integer | Primary key |
| Name | String | Contact name |
| Department | String | Department |
| OrgNr | String | VAT number or similar |
| Number1 | String | Alphanumeric user field |
| Number2 | String | Alphanumeric user field |
| UpdatedDate | String | Date last updated  in UTC. |
| CreatedDate | String | Date registered  in UTC. |
| Emails | Array | The contact's email |
| Interests | Array | The contact's available and selected interests.  <para>Use MDO List name "contint" to get list items.</para> |
| Urls | Array | The contact's internet adresses |
| Phones | Array | The contact's phone numbers |
| Faxes | Array | The contact's fax numbers |
| Description | String | Description of the contact. Usually shown as a postit note. |
| UpdatedBy | Associate | The user that last updated the contact |
| CreatedBy | Associate | The user that created the contact |
| Associate | Associate | The user that owns this contact.  <para>Use MDO List name "associate" to get list items.</para> |
| Business | Business | The business that the contact is associated with. The GUI forces the user to enter a business type.  <para>Use MDO List name "business" to get list items.</para> |
| Category | Category | The category that is set on the company. The GUI forces the user to enter a category type  <para>Use MDO List name "category" to get list items.</para> |
| Country | Country | The country this contact is located in. The country a contact is saved with, affects the phone number format, and the address layout.  <para>Use MDO List name "country" to get list items.</para> |
| Persons | Array | The persons belonging to the contact. |
| NoMailing | Boolean | Spam filter. Indicates if this contact should retrieve advertising. |
| Kananame | String | Contact kana name, used in Japanese versions only |
| Xstop | Boolean | STOP flag |
| ActiveInterests | Integer | The number of active interests. |
| GroupId | Integer | Group id of original owning associate, semantics like appnt.grp_id |
| ActiveStatusMonitorId | Integer | Active status monitor identity with the lowest rank for contact |
| SupportAssociate | Associate | <para>Use MDO List name "associate" to get list items.</para> |
| TicketPriority | TicketPriority | <para>Use MDO List name "ticketpriority" to get list items.</para> |
| CustomerLanguage | CustomerLanguage | customerlanguage |
| Deleted | Integer | If nonzero, then this contact is 'deleted' and should generally not be shown |
| DbiAgentId | Integer | Integration agent (eJournal) |
| DbiLastSyncronized | String | Last external syncronization. |
| DbiKey | String | The primary key for the integrated entry in the external datasource. |
| DbiLastModified | String | When the entry was last modified. |
| SupportPerson | Person | Carrier object for Person. Services for the Person Carrier is available from the <see cref="T:SuperOffice.CRM.Services.IPersonAgent">Person Agent</see>. |
| Address | Address | Street and/or Postal address, in both formatted and structured forms. You only need to modify one of the two for the change to be registered. <para /> Carrier object for Address. |
| Source | Integer | How did we get this contact? For future integration needs |
| ActiveErpLinks | Integer | The number of active erp links |
| BounceEmails | Array | Email addresses with a positive bounce counter. |
| Domains | Array | Web domains for this contact, ordered in array by rank |
| UserDefinedFields | Object | Deprecated: Use {SuperOffice.CRM.Services.ContactEntity.CustomFields} instead. Dictionary of user defined field data. The key string is the ProgId of the UdefField, or if the ProgId is empty it is a string of the format "SuperOffice:[UdefFieldIdentity]", e.g. "SuperOffice:1234" |
| ExtraFields | Object | Deprecated: Use {SuperOffice.CRM.Services.ContactEntity.CustomFields} instead. Extra fields added to the carrier. This could be data from Plug-ins, the foreign key system, external applications, etc. |
| CustomFields | Object | Udef + Extra fields added to the carrier. Extra fields as defined by changes to database schema + user-defined fields as defined by admin. Custom fields combines user defined fields and extra fields into one bucket.  The individual {SuperOffice.CRM.Services.ContactEntity.ExtraFields} and <see cref="P:SuperOffice.CRM.Services.ContactEntity.UserDefinedFields">UserDefinedFields</see> properties are deprecated in favor of this combined collection. |

## Response:object

OK

| Response | Description |
|----------------|-------------|
| 200 | OK |

### Response body: object


## Sample request

```http!
POST /api/v1/Contact/Validate
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: *
Content-Type: application/json; charset=utf-8

{
  "ContactId": 628,
  "Name": "Treutel LLC",
  "Department": "",
  "OrgNr": "1381083",
  "Number1": "991794",
  "Number2": "1507662",
  "UpdatedDate": "2012-05-03T03:31:32.4726896+02:00",
  "CreatedDate": "2014-02-03T03:31:32.4726896+01:00",
  "Emails": [
    {
      "Value": "rerum",
      "StrippedValue": "laborum",
      "Description": "Customer-focused systematic interface"
    },
    {
      "Value": "rerum",
      "StrippedValue": "laborum",
      "Description": "Customer-focused systematic interface"
    }
  ],
  "Interests": [
    {
      "Id": 339,
      "Name": "Deckow-Becker",
      "ToolTip": "Sequi doloremque ut corporis.",
      "Deleted": false,
      "Rank": 323,
      "Type": "reiciendis",
      "ColorBlock": 219,
      "IconHint": "a",
      "Selected": false,
      "LastChanged": "1999-06-03T03:31:32.4726896+02:00",
      "ChildItems": [
        {},
        {}
      ],
      "ExtraInfo": "itaque",
      "StyleHint": "ipsam",
      "Hidden": false,
      "FullName": "Mr. Jarvis Hayes"
    }
  ],
  "Urls": [
    {
      "Value": "voluptatem",
      "StrippedValue": "autem",
      "Description": "Synergistic 5th generation moderator"
    },
    {
      "Value": "voluptatem",
      "StrippedValue": "autem",
      "Description": "Synergistic 5th generation moderator"
    }
  ],
  "Phones": [
    {
      "Value": "error",
      "StrippedValue": "amet",
      "Description": "Customer-focused exuding firmware"
    },
    {
      "Value": "error",
      "StrippedValue": "amet",
      "Description": "Customer-focused exuding firmware"
    }
  ],
  "Faxes": [
    {
      "Value": "voluptatum",
      "StrippedValue": "magni",
      "Description": "Ergonomic neutral function"
    },
    {
      "Value": "voluptatum",
      "StrippedValue": "magni",
      "Description": "Ergonomic neutral function"
    }
  ],
  "Description": "User-friendly client-server adapter",
  "UpdatedBy": null,
  "CreatedBy": null,
  "Associate": null,
  "Business": null,
  "Category": null,
  "Country": null,
  "Persons": [
    {
      "Position": "error",
      "PersonId": 56,
      "Mrmrs": "ad",
      "Firstname": "Fiona",
      "Lastname": "Boyer",
      "MiddleName": "Fay Group",
      "Title": "reprehenderit",
      "Description": "Public-key fresh-thinking framework",
      "Email": "monserrat@braunfritsch.ca",
      "FullName": "Dario Pacocha",
      "DirectPhone": "508-946-7257 x2126",
      "FormalName": "Paucek LLC",
      "CountryId": 498,
      "ContactId": 400,
      "ContactName": "Lueilwitz LLC",
      "Retired": 417,
      "Rank": 103,
      "ActiveInterests": 807,
      "ContactDepartment": "",
      "ContactCountryId": 873,
      "ContactOrgNr": "389019",
      "FaxPhone": "(242)726-7971 x062",
      "MobilePhone": "(927)586-4315 x670",
      "ContactPhone": "(928)188-3073 x20394",
      "AssociateName": "Balistreri Group",
      "AssociateId": 700,
      "UsePersonAddress": false,
      "ContactFax": "voluptatem",
      "Kanafname": "nostrum",
      "Kanalname": "dolorem",
      "Post1": "ipsa",
      "Post2": "earum",
      "Post3": "facilis",
      "EmailName": "dusty.schimmel@schmittschowalter.co.uk",
      "ContactFullName": "Julia Sporer",
      "ActiveErpLinks": 642,
      "TicketPriorityId": 224,
      "SupportLanguageId": 528,
      "SupportAssociateId": 338,
      "CategoryName": "VIP Customer"
    }
  ],
  "NoMailing": true,
  "Kananame": "accusamus",
  "Xstop": true,
  "ActiveInterests": 255,
  "GroupId": 491,
  "ActiveStatusMonitorId": 693,
  "SupportAssociate": null,
  "TicketPriority": null,
  "CustomerLanguage": null,
  "Deleted": 605,
  "DbiAgentId": 943,
  "DbiLastSyncronized": "2007-09-12T03:31:32.4726896+02:00",
  "DbiKey": "doloribus",
  "DbiLastModified": "2022-10-18T03:31:32.4726896+02:00",
  "SupportPerson": null,
  "Address": null,
  "Source": 930,
  "ActiveErpLinks": 783,
  "BounceEmails": [
    "viviane.upton@ruecker.us",
    "ethelyn@graham.us"
  ],
  "Domains": [
    "voluptatem",
    "omnis"
  ],
  "UserDefinedFields": {
    "SuperOffice:1": "Keon Larkin",
    "SuperOffice:2": "False"
  },
  "ExtraFields": {
    "ExtraFields1": "officiis",
    "ExtraFields2": "explicabo"
  },
  "CustomFields": {
    "CustomFields1": "illo",
    "CustomFields2": "in"
  }
}
```

## Sample response

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "1": "consequatur",
  "2": "natus"
}
```