---
title: POST Agents/List/SaveTicketPriorityEntity
uid: v1ListAgent_SaveTicketPriorityEntity
generated: true
---

# POST Agents/List/SaveTicketPriorityEntity

```http
POST /api/v1/Agents/List/SaveTicketPriorityEntity
```

Updates the existing TicketPriorityEntity or creates a new TicketPriorityEntity if the id parameter is empty








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

The TicketPriorityEntity to be saved. 

| Property Name | Type |  Description |
|----------------|------|--------------|
| TicketPriorityId | Integer | The primary key (auto-incremented) |
| Name | String | The name of the priority. |
| Status | String | The status (normal/deleted) of the priority. |
| Flags | String | A bitmask of flags. |
| SortOrder | Integer | Indicates the sort order for this priority. 1 is first, 100 is last |
| TicketRead | String | This field indicates what to do with the escalation chain when the request is read |
| ChangedOwner | String | This field indicates what to do with the escalation chain when the request changes owner (manually) |
| TicketNewinfo | String | This field indicates what to do with the escalation chain when the request gets new info |
| TicketClosed | String | This field indicates what to do with the escalation chain when the request is closed |
| TicketChangedPriority | String | This field indicates what to do with the escalation chain when the request is changed into this priority |
| TicketNew | String | This field indicates what to do with the escalation chain when a new request is registered |
| Deadline | Integer | Deadline to add if escalated (minutes) |
| MonStart | String | The work hour start for Mondays. Note that only the time part of the DateTime is used |
| MonStop | String | The work hour start for Mondays. Note that only the time part of the DateTime is used |
| TueStart | String | The work hour start for Tuesdays. Note that only the time part of the DateTime is used |
| TueStop | String | The work hour stop for Tuesdays. Note that only the time part of the DateTime is used |
| WedStart | String | The work hour start for Wednesdays. Note that only the time part of the DateTime is used |
| WedStop | String | The work hour stop for Wednesdays. Note that only the time part of the DateTime is used |
| ThuStart | String | The work hour start for Thursdays. Note that only the time part of the DateTime is used |
| ThuStop | String | The work hour stop for Thursdays. Note that only the time part of the DateTime is used |
| FriStart | String | The work hour start for Fridays. Note that only the time part of the DateTime is used |
| FriStop | String | The work hour stop for Fridays. Note that only the time part of the DateTime is used |
| SatStart | String | The work hour start for Saturdays. Note that only the time part of the DateTime is used |
| SatStop | String | The work hour stop for Saturdays. Note that only the time part of the DateTime is used |
| SunStart | String | The work hour start for Sundays. Note that only the time part of the DateTime is used |
| SunStop | String | The work hour stop for Sundays. Note that only the time part of the DateTime is used |
| NonDates | Array | Dates which the escalation time should not be running. Note that only the day of the year (day and month) is used. So the year and time part is not used even if this is a DateTime. Exception - it IS possible to include a year here, for dates that should not repeat every year |
| EscalationLevels | Array | Escalation levels bound to the parent priority |

## Response:

OK

| Response | Description |
|----------------|-------------|
| 200 | OK |

### Response body: TicketPriorityEntity

| Property Name | Type |  Description |
|----------------|------|--------------|
| TicketPriorityId | int32 | The primary key (auto-incremented) |
| Name | string | The name of the priority. |
| Status | string | The status (normal/deleted) of the priority. |
| Flags | string | A bitmask of flags. |
| SortOrder | int32 | Indicates the sort order for this priority. 1 is first, 100 is last |
| TicketRead | string | This field indicates what to do with the escalation chain when the request is read |
| ChangedOwner | string | This field indicates what to do with the escalation chain when the request changes owner (manually) |
| TicketNewinfo | string | This field indicates what to do with the escalation chain when the request gets new info |
| TicketClosed | string | This field indicates what to do with the escalation chain when the request is closed |
| TicketChangedPriority | string | This field indicates what to do with the escalation chain when the request is changed into this priority |
| TicketNew | string | This field indicates what to do with the escalation chain when a new request is registered |
| Deadline | int32 | Deadline to add if escalated (minutes) |
| MonStart | date-time | The work hour start for Mondays. Note that only the time part of the DateTime is used |
| MonStop | date-time | The work hour start for Mondays. Note that only the time part of the DateTime is used |
| TueStart | date-time | The work hour start for Tuesdays. Note that only the time part of the DateTime is used |
| TueStop | date-time | The work hour stop for Tuesdays. Note that only the time part of the DateTime is used |
| WedStart | date-time | The work hour start for Wednesdays. Note that only the time part of the DateTime is used |
| WedStop | date-time | The work hour stop for Wednesdays. Note that only the time part of the DateTime is used |
| ThuStart | date-time | The work hour start for Thursdays. Note that only the time part of the DateTime is used |
| ThuStop | date-time | The work hour stop for Thursdays. Note that only the time part of the DateTime is used |
| FriStart | date-time | The work hour start for Fridays. Note that only the time part of the DateTime is used |
| FriStop | date-time | The work hour stop for Fridays. Note that only the time part of the DateTime is used |
| SatStart | date-time | The work hour start for Saturdays. Note that only the time part of the DateTime is used |
| SatStop | date-time | The work hour stop for Saturdays. Note that only the time part of the DateTime is used |
| SunStart | date-time | The work hour start for Sundays. Note that only the time part of the DateTime is used |
| SunStop | date-time | The work hour stop for Sundays. Note that only the time part of the DateTime is used |
| NonDates | array | Dates which the escalation time should not be running. Note that only the day of the year (day and month) is used. So the year and time part is not used even if this is a DateTime. Exception - it IS possible to include a year here, for dates that should not repeat every year |
| EscalationLevels | array | Escalation levels bound to the parent priority |
| TableRight | TableRight | The carrier's table right |
| FieldProperties | object | Field property dictionary mapping field names to field access rights. |

## Sample request

```http!
POST /api/v1/Agents/List/SaveTicketPriorityEntity
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: en
Content-Type: application/json; charset=utf-8

{
  "TicketPriorityId": 962,
  "Name": "Kuhlman-Leannon",
  "Status": "Deleted",
  "Flags": "AlertSchedule",
  "SortOrder": 779,
  "TicketRead": "Continue",
  "ChangedOwner": "Continue",
  "TicketNewinfo": "Continue",
  "TicketClosed": "Continue",
  "TicketChangedPriority": "Continue",
  "TicketNew": "Continue",
  "Deadline": 14,
  "MonStart": "2012-08-22T03:31:26.7456608+02:00",
  "MonStop": "2022-03-17T03:31:26.7456608+01:00",
  "TueStart": "2003-11-26T03:31:26.7456608+01:00",
  "TueStop": "2014-08-30T03:31:26.7456608+02:00",
  "WedStart": "2007-08-17T03:31:26.7456608+02:00",
  "WedStop": "1998-07-17T03:31:26.7456608+02:00",
  "ThuStart": "2022-06-22T03:31:26.7456608+02:00",
  "ThuStop": "2001-11-09T03:31:26.7456608+01:00",
  "FriStart": "2022-05-18T03:31:26.7456608+02:00",
  "FriStop": "2016-01-23T03:31:26.7456608+01:00",
  "SatStart": "2017-11-12T03:31:26.7456608+01:00",
  "SatStop": "1996-09-13T03:31:26.7456608+02:00",
  "SunStart": "2002-05-09T03:31:26.7456608+02:00",
  "SunStop": "2001-01-07T03:31:26.7456608+01:00",
  "NonDates": [
    "fugit",
    "quas"
  ],
  "EscalationLevels": [
    {
      "TicketAlertId": 370,
      "AlertLevel": 509,
      "AlertTimeout": 112,
      "Action": 920,
      "DelegateTo": 637,
      "ScriptId": 239,
      "EmailTo": "guy@botsforderdman.biz",
      "SmsTo": "dolor",
      "ReplyTemplateIdCustomer": 57,
      "ReplyTemplateIdUser": 818,
      "ReplyTemplateIdCatmast": 41,
      "ReplyTemplateIdEmail": 908,
      "RtiCustomerSms": 437,
      "ReplyTemplateIdUserSms": 52,
      "ReplyTemplateIdCatmastSms": 410,
      "ReplyTemplateIdSms": 495
    }
  ]
}
```

## Sample response

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "TicketPriorityId": 479,
  "Name": "Sanford, Ziemann and Prohaska",
  "Status": "Deleted",
  "Flags": "AlertSchedule",
  "SortOrder": 330,
  "TicketRead": "Continue",
  "ChangedOwner": "Continue",
  "TicketNewinfo": "Continue",
  "TicketClosed": "Continue",
  "TicketChangedPriority": "Continue",
  "TicketNew": "Continue",
  "Deadline": 888,
  "MonStart": "2009-08-23T03:31:26.7456608+02:00",
  "MonStop": "2017-05-24T03:31:26.7456608+02:00",
  "TueStart": "2019-07-26T03:31:26.7456608+02:00",
  "TueStop": "2020-04-19T03:31:26.7456608+02:00",
  "WedStart": "2008-12-01T03:31:26.7456608+01:00",
  "WedStop": "2021-01-01T03:31:26.7456608+01:00",
  "ThuStart": "2009-08-14T03:31:26.7456608+02:00",
  "ThuStop": "2020-12-18T03:31:26.7456608+01:00",
  "FriStart": "2017-01-10T03:31:26.7456608+01:00",
  "FriStop": "2021-09-16T03:31:26.7456608+02:00",
  "SatStart": "2019-08-29T03:31:26.7456608+02:00",
  "SatStop": "2012-07-18T03:31:26.7456608+02:00",
  "SunStart": "2007-12-07T03:31:26.7456608+01:00",
  "SunStop": "1999-08-14T03:31:26.7456608+02:00",
  "NonDates": [
    "qui",
    "aut"
  ],
  "EscalationLevels": [
    {
      "TicketAlertId": 574,
      "AlertLevel": 397,
      "AlertTimeout": 51,
      "Action": 644,
      "DelegateTo": 135,
      "ScriptId": 969,
      "EmailTo": "verna@borer.uk",
      "SmsTo": "porro",
      "ReplyTemplateIdCustomer": 795,
      "ReplyTemplateIdUser": 830,
      "ReplyTemplateIdCatmast": 799,
      "ReplyTemplateIdEmail": 203,
      "RtiCustomerSms": 442,
      "ReplyTemplateIdUserSms": 486,
      "ReplyTemplateIdCatmastSms": 223,
      "ReplyTemplateIdSms": 522,
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.String",
          "FieldLength": 841
        }
      }
    }
  ],
  "TableRight": null,
  "FieldProperties": {
    "fieldName": {
      "FieldRight": null,
      "FieldType": "System.Int32",
      "FieldLength": 743
    }
  }
}
```