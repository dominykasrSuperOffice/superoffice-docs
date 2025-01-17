---
title: PUT List/DeliveryType/Items/{id}/Headings
uid: v1DeliveryTypeList_PutDeliveryTypeHeadingsForListItem
generated: true
---

# PUT List/DeliveryType/Items/{id}/Headings

```http
PUT /api/v1/List/DeliveryType/Items/{itemId}/Headings
```

Saves headings for the DeliveryType list's item.


Calls the List agent service SaveHeadingsForListItemFromListDefinition.





| Path Part | Type | Description |
|-----------|------|-------------|
| itemId | int32 | The ID of the headings to be saved. **Required** |



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

## Request Body: entities 

The headings to be saved. 

| Property Name | Type |  Description |
|----------------|------|--------------|
| Id | Integer | The Id of the ListItem |
| Name | String | The name of the ListItem |
| ToolTip | String | The tooltip of the ListItem |
| Deleted | Boolean | The deleted status of the ListItem |
| Rank | Integer | The rank of the ListItem |
| Type | String | The type of the ListItem. Custom field. |
| ColorBlock | Integer | The color indicator of the ListItem color block |
| IconHint | String | The Icon hint of the ListItem. Custom field. |
| Selected | Boolean | True if the ListItem is selected |
| LastChanged | String | Time of last change. |
| ChildItems | Array | The child items of the SelectableMDOListItem |
| ExtraInfo | String | Extra information added to the ListItem. Could be information such as sort order etc or other meta data. Custom field. |
| StyleHint | String | Style hint indicating, information such as background color etc. Custom field. |
| Hidden | Boolean | True if the ListItem is hidden |
| FullName | String | The name of the ListItem in its context |

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
PUT /api/v1/List/DeliveryType/Items/{itemId}/Headings
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: sv
Content-Type: application/json; charset=utf-8

[
  {
    "Id": 805,
    "Name": "Nitzsche-Kuvalis",
    "ToolTip": "Ea id.",
    "Deleted": false,
    "Rank": 672,
    "Type": "ipsam",
    "ColorBlock": 57,
    "IconHint": "odio",
    "Selected": true,
    "LastChanged": "2016-10-17T03:31:33.6167125+02:00",
    "ChildItems": [
      {
        "Id": 606,
        "Name": "Medhurst Group",
        "ToolTip": "Fuga temporibus.",
        "Deleted": false,
        "Rank": 541,
        "Type": "repellat",
        "ColorBlock": 942,
        "IconHint": "repellendus",
        "Selected": false,
        "LastChanged": "2006-11-25T03:31:33.6167125+01:00",
        "ChildItems": [
          {},
          {}
        ],
        "ExtraInfo": "cumque",
        "StyleHint": "quis",
        "Hidden": false,
        "FullName": "Laron Wehner PhD"
      }
    ],
    "ExtraInfo": "in",
    "StyleHint": "voluptas",
    "Hidden": false,
    "FullName": "Miss Dedric Durgan II"
  }
]
```

## Sample response

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

[
  {
    "Id": 192,
    "Name": "Farrell Inc and Sons",
    "ToolTip": "Neque et dolorem quidem ut officia a.",
    "Deleted": true,
    "Rank": 56,
    "Type": "provident",
    "ColorBlock": 672,
    "IconHint": "nesciunt",
    "Selected": false,
    "LastChanged": "2013-02-08T03:31:33.6167125+01:00",
    "ChildItems": [
      {
        "Id": 552,
        "Name": "Sawayn-Jacobs",
        "ToolTip": "Incidunt ipsam est omnis sed.",
        "Deleted": false,
        "Rank": 728,
        "Type": "provident",
        "ColorBlock": 756,
        "IconHint": "dicta",
        "Selected": false,
        "LastChanged": "1998-12-07T03:31:33.6167125+01:00",
        "ChildItems": [
          {},
          {}
        ],
        "ExtraInfo": "quis",
        "StyleHint": "corrupti",
        "Hidden": false,
        "FullName": "Miss Kristofer Carson Abshire",
        "TableRight": null,
        "FieldProperties": {
          "fieldName": {
            "FieldRight": null,
            "FieldType": "System.Int32",
            "FieldLength": 365
          }
        }
      }
    ],
    "ExtraInfo": "accusantium",
    "StyleHint": "fugiat",
    "Hidden": false,
    "FullName": "Jedediah Rutherford",
    "TableRight": null,
    "FieldProperties": {
      "fieldName": {
        "FieldRight": null,
        "FieldType": "System.Int32",
        "FieldLength": 49
      }
    }
  }
]
```