---
title: GET List/ProjectType/Items/{id}/UserGroups
uid: v1ProjectTypeList_GetProjectTypeUserGroupsForListItem
generated: true
---

# GET List/ProjectType/Items/{id}/UserGroups

```http
GET /api/v1/List/ProjectType/Items/{itemId}/UserGroups
```

Gets user groups visible for the ProjectType list's item.


Calls the List agent service GetHeadings.





| Path Part | Type | Description |
|-----------|------|-------------|
| itemId | int32 | The ID of the item to get. **Required** |



## Request Headers

| Parameter Name | Description |
|----------------|-------------|
| Authorization  | Supports 'Basic', 'SoTicket' and 'Bearer' schemes, depending on installation type. |
| X-XSRF-TOKEN   | If not using Authorization header, you must provide XSRF value from cookie or hidden input field |
| Accept         | Content-type(s) you would like the response in: `application/json`, `text/json`, `application/xml`, `text/xml`, `application/json-patch+json`, `application/merge-patch+json` |
| Accept-Language | Convert string references and multi-language values into a specified language (iso2) code. |
| SO-Language | Convert string references and multi-language values into a specified language (iso2) code. Overrides Accept-Language value. |
| SO-Culture | Number, date formatting in a specified culture (iso2 language) code. Partially overrides SO-Language/Accept-Language value. Ignored if no Language set. |
| SO-TimeZone | Specify the timezone code that you would like date/time responses converted to. |
| SO-AppToken | The application token that identifies the partner app. Used when calling Online WebAPI from a server. |


## Response:array

OK

| Response | Description |
|----------------|-------------|
| 200 | OK |

### Response body: array

| Property Name | Type |  Description |
|----------------|------|--------------|
| Id | int32 | The Id of the ListItem |
| Name | string | The name of the ListItem |
| ToolTip | string | The tooltip of the ListItem |
| Deleted | bool | The deleted status of the ListItem |
| Rank | int32 | The rank of the ListItem |
| Type | string | The type of the ListItem. Custom field. |
| ColorBlock | int32 | The color indicator of the ListItem color block |
| IconHint | string | The Icon hint of the ListItem. Custom field. |
| Selected | bool | True if the ListItem is selected |
| LastChanged | date-time | Time of last change. |
| ChildItems | array | The child items of the SelectableMDOListItem |
| ExtraInfo | string | Extra information added to the ListItem. Could be information such as sort order etc or other meta data. Custom field. |
| StyleHint | string | Style hint indicating, information such as background color etc. Custom field. |
| Hidden | bool | True if the ListItem is hidden |
| FullName | string | The name of the ListItem in its context |
| TableRight | TableRight | The carrier's table right |
| FieldProperties | object | Field property dictionary mapping field names to field access rights. |

## Sample request

```http!
GET /api/v1/List/ProjectType/Items/{itemId}/UserGroups
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: *
```

## Sample response

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

[
  {
    "Id": 22,
    "Name": "Stanton, Walsh and Bins",
    "ToolTip": "Consequuntur sit velit amet id quam rerum aut.",
    "Deleted": false,
    "Rank": 106,
    "Type": "amet",
    "ColorBlock": 65,
    "IconHint": "architecto",
    "Selected": false,
    "LastChanged": "2011-11-05T03:31:33.7742322+01:00",
    "ChildItems": [
      {
        "Id": 709,
        "Name": "Erdman LLC",
        "ToolTip": "Consequatur ea et qui tempore esse.",
        "Deleted": true,
        "Rank": 991,
        "Type": "et",
        "ColorBlock": 258,
        "IconHint": "fugit",
        "Selected": false,
        "LastChanged": "2007-07-02T03:31:33.7742322+02:00",
        "ChildItems": [
          {},
          {}
        ],
        "ExtraInfo": "quo",
        "StyleHint": "iste",
        "Hidden": true,
        "FullName": "Ellis Stroman DDS",
        "TableRight": null,
        "FieldProperties": {
          "fieldName": {
            "FieldRight": null,
            "FieldType": "System.Int32",
            "FieldLength": 642
          }
        }
      }
    ],
    "ExtraInfo": "ipsum",
    "StyleHint": "vel",
    "Hidden": true,
    "FullName": "Zetta Sabina Wunsch IV",
    "TableRight": null,
    "FieldProperties": {
      "fieldName": {
        "FieldRight": null,
        "FieldType": "System.Int32",
        "FieldLength": 784
      }
    }
  }
]
```