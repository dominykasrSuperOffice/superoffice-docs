---
title: PUT Hierarchy/{domain}/{path}
uid: v1HierarchyEntity_UpdateHierarchyFromPath
generated: true
---

# PUT Hierarchy/{domain}/{path}

```http
PUT /api/v1/Hierarchy/{domain}/{path}
```

Update a hierarchy item from a path






| Path Part | Type | Description |
|-----------|------|-------------|
| domain | Enum: Unknown, ExtraTables, ScreenDefinitions, Scripts, Selections, ExternalDocuments, UserGroups, ExternalDocumentRelatedToSpmMessage, Dashboards, EmailFlows | Type of items to get **Required** |
| path | string | Hierarchy path to item **Required** |



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

## Request Body: entity 

The hierarchy node to update. 

| Property Name | Type |  Description |
|----------------|------|--------------|
| HierarchyId | Integer | The primary key (auto-incremented) |
| Domain | String | Domain seperating the different hierarchy |
| Name | String | Name of this hierarchy folder. |
| Fullname | String | The full name of this category, i.e. Foo/bar/test. |
| ParentId | Integer | Parent table |
| Children | Array | Sub-items, if any. |
| Registered | String | Registered when  in UTC. |
| RegisteredAssociateId | Integer | Registered by whom |
| Updated | String | Last updated when  in UTC. |
| UpdatedAssociateId | Integer | Last updated by whom |

## Response:

OK

| Response | Description |
|----------------|-------------|
| 200 | OK |

### Response body: HierarchyEntity

| Property Name | Type |  Description |
|----------------|------|--------------|
| HierarchyId | int32 | The primary key (auto-incremented) |
| Domain | string | Domain seperating the different hierarchy |
| Name | string | Name of this hierarchy folder. |
| Fullname | string | The full name of this category, i.e. Foo/bar/test. |
| ParentId | int32 | Parent table |
| Children | array | Sub-items, if any. |
| Registered | date-time | Registered when  in UTC. |
| RegisteredAssociateId | int32 | Registered by whom |
| Updated | date-time | Last updated when  in UTC. |
| UpdatedAssociateId | int32 | Last updated by whom |
| TableRight | TableRight | The carrier's table right |
| FieldProperties | object | Field property dictionary mapping field names to field access rights. |

## Sample request

```http!
PUT /api/v1/Hierarchy/{domain}/{path}
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: en
Content-Type: application/json; charset=utf-8

{
  "HierarchyId": 314,
  "Domain": "Dashboards",
  "Name": "Macejkovic, Beier and Stiedemann",
  "Fullname": "repudiandae",
  "ParentId": 225,
  "Children": [
    {
      "HierarchyId": 753,
      "Domain": "Dashboards",
      "Name": "Klocko-Weimann",
      "Fullname": "ullam",
      "ParentId": 538,
      "Children": [
        {},
        {}
      ],
      "Registered": "2002-06-30T03:31:32.6289016+02:00",
      "RegisteredAssociateId": 129,
      "Updated": "2000-04-08T03:31:32.6289016+02:00",
      "UpdatedAssociateId": 391
    }
  ],
  "Registered": "1998-08-17T03:31:32.6289016+02:00",
  "RegisteredAssociateId": 187,
  "Updated": "1996-07-29T03:31:32.6289016+02:00",
  "UpdatedAssociateId": 506
}
```

## Sample response

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "HierarchyId": 500,
  "Domain": "Dashboards",
  "Name": "Gibson-Toy",
  "Fullname": "consequatur",
  "ParentId": 174,
  "Children": [
    {
      "HierarchyId": 1002,
      "Domain": "Dashboards",
      "Name": "Gutkowski Inc and Sons",
      "Fullname": "eaque",
      "ParentId": 813,
      "Children": [
        {},
        {}
      ],
      "Registered": "2001-09-16T03:31:32.6289016+02:00",
      "RegisteredAssociateId": 810,
      "Updated": "2016-05-06T03:31:32.6289016+02:00",
      "UpdatedAssociateId": 208,
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 296
        }
      }
    }
  ],
  "Registered": "2006-02-04T03:31:32.6289016+01:00",
  "RegisteredAssociateId": 246,
  "Updated": "2020-09-19T03:31:32.6289016+02:00",
  "UpdatedAssociateId": 828,
  "TableRight": null,
  "FieldProperties": {
    "fieldName": {
      "FieldRight": null,
      "FieldType": "System.String",
      "FieldLength": 668
    }
  }
}
```